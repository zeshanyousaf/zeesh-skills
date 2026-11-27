# YouTube Shorts Extractor

## Analyze a video and score candidates

- Run the analyzer from `~/workspace/tools/yt-shorts` with the venv Python and pass a YouTube link or a local video file.

```bash
cd ~/workspace/tools/yt-shorts
./venv/bin/python yt_shorts.py analyze "<youtube_url>" [--count 3] [--model base]
./venv/bin/python yt_shorts.py analyze /path/to/video.mp4 [--count 3]
```

- The analyzer downloads up to 720p mp4 and extracts mono 16kHz audio for faster-whisper transcription with word level timestamps.

- The scorer ranks candidate windows of about 40 to 75 seconds on hook words, questions, numbers, punctuation, personal story signals and speech density.

- The analyzer saves `transcript.txt`, `transcript.json` and `candidates.json` in `jobs/<job_id>/` and reuses cached `video.mp4` and `audio.wav` on re-runs.

- The local whisper model lives in `~/workspace/tools/yt-shorts/models/base/` and runs offline with no download, and `--model local` maps there too.

- Budget about 1 to 2 minutes of CPU transcription per 10 minutes of video with the base model.

- YouTube throttles aggressively with TLS errors, 429 responses and bot checks, so ask the user for the video file or try again later when a URL analyze fails.

- Behind this sandbox egress proxy, yt-dlp ignores `SSL_CERT_FILE` and `REQUESTS_CA_BUNDLE` because it loads the certifi bundle explicitly, so append the proxy CA once to the venv certifi bundle with `cat /run/hatch/egress-tls/hatch-egress-ca.pem >> venv/lib/python3.12/site-packages/certifi/cacert.pem`.

- A 403 at the very end of a download is YouTube throttling, so resume with `yt-dlp -c` and it usually completes.

## Render vertical clips with burned-in captions

- Render from the analyzed job with automatic picks or hand picked segments.

```bash
./venv/bin/python yt_shorts.py render --job jobs/<job_id> --auto [--count 3]
./venv/bin/python yt_shorts.py render --job jobs/<job_id> --picks '[{"start":12.5,"end":72.5,"title":"..."}]'
```

- The renderer center crops to 9:16 and scales to 1080x1920 and never does a landscape then crop pass.

- Captions burn in as ASS text in big bold white with a black outline at bottom center, using Noto Sans Arabic for Urdu, Arabic and Persian and DejaVu Sans for other languages.

- The renderer encodes H.264 at veryfast and CRF 20 plus AAC at 128k with faststart and writes `short_01.mp4` and following clips plus `cap_N.ass`, `manifest.json` and `titles.md`.

- The scorer may return fewer shorts than the requested count when the video has few strong moments.

- Titles in `titles.md` are heuristic drafts, so review the file and rewrite the title line before the user posts and prefer a self contained hook over an opening fragment.

- Never run two render commands against the same job at the same time because they write the same output files and corrupt each other.

## Verify before you deliver

- Run ffprobe and a clean decode check on each finished file and extract one frame to eyeball the captions.

```bash
f=~/workspace/your_files/yt-shorts/<job_id>/short_01.mp4
ffprobe -v error -show_entries stream=width,height,codec_name -of default=noprint_wrappers=1 "$f"
ffmpeg -v error -i "$f" -f null -
ffmpeg -y -v error -ss 5 -i "$f" -frames:v 1 /tmp/check.png
```

- Confirm 1080x1920 with H.264 plus AAC and a sensible duration of about 40 to 75 seconds.

- Open the extracted frame and look to confirm the captions are burned in, because ASS Dialogue lines must carry all 10 fields and missing fields render zero events.

- Deliver the finished clips from `~/workspace/your_files/yt-shorts/<job_id>/` and report the job id with each delivery.

## Do not use this pipeline for paid clipping

- This pipeline downloads up to 720p and scales the result to 1080x1920, so its output is upscaled and not a verified 1080p source.

- Paid clipping campaigns require a verified 1080p VOD source, so build paid clips with [Paid Clipping Campaigns](/home/hatch/workspace/custom-skills/paid_clipping_campaigns/SKILL.md) instead of this pipeline.

- Never call an upscaled clip HD and never deliver one as a paid campaign clip.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Websites

- [YouTube](https://www.youtube.com/) for the source long video. Carry the exact video link into the analyze command and fall back to a local file when the download is blocked.

## Alternatives for better results

- Ask the user for the video file when YouTube blocks the download instead of retrying the URL in a loop.

- Review `titles.md` and rewrite each title line before the user posts, preferring a self contained hook.

- Score more candidates than you plan to render and keep only the strongest moments.
