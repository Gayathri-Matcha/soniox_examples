# Soniox examples

## 1. Get API key

Create a free [Soniox account](https://console.soniox.com/signup) and log in to the [Console](https://console.soniox.com) to get your API key.

API keys are created per project. In the Console, go to **My First Project** and click **API Keys** to generate one.

Export it as an environment variable (replace with your key):

```sh
export SONIOX_API_KEY=<your_soniox_api_key>
```

## 2. Get examples

Clone the official examples repo:

```sh
git clone https://github.com/soniox/soniox_examples
cd soniox_examples/speech_to_text
```

## 3. Run examples

Run the ready-to-use examples below.

| Example                                | What it does                                                                                                            | Output                                                     |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| **Real-time <br> transcription**       | Transcribes speech in any language in real time.                                                                        | Transcript streamed to console.                            |
| **Real-time <br> one-way translation** | Transcribes speech in any language and translates it into Spanish in real time.                                         | Transcript + Spanish translation streamed together.        |
| **Real-time <br> two-way translation** | Transcribes speech in any language and translates English ↔ Spanish in real time. Spanish → English, English → Spanish. | Transcript + bidirectional translations streamed together. |
| **Transcribe <br> file from URL**      | Transcribes an audio file directly from a public URL.                                                                   | Transcript printed to console.                             |
| **Transcribe <br> local file**         | Uploads and transcribes an audio file from your computer.                                                               | Transcript printed to console.                             |

<details open>
<summary><b>Python</b></summary>

```sh
# Set up environment
cd python
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Real-time examples
python soniox_realtime.py --audio_path ../assets/coffee_shop.mp3
python soniox_realtime.py --audio_path ../assets/coffee_shop.pcm_s16le --audio_format pcm_s16le
python soniox_realtime.py --audio_path ../assets/coffee_shop.mp3 --translation one_way
python soniox_realtime.py --audio_path ../assets/two_way_translation.mp3 --translation two_way

# Async examples
python soniox_async.py --audio_url "https://soniox.com/media/examples/coffee_shop.mp3"
python soniox_async.py --audio_path ../assets/coffee_shop.mp3
python soniox_async.py --delete_all_files
python soniox_async.py --delete_all_transcriptions
```

</details>

<details>
<summary><b>Node.js</b></summary>

```sh
# Set up environment
cd nodejs
npm install

# Real-time examples
node soniox_realtime.js --audio_path ../assets/coffee_shop.mp3
node so

node soniox_realtime.js --audio_path ../assets/coffee_shop.pcm_s16le --audio_format pcm_s16le
node soniox_realtime.js --audio_path ../assets/coffee_shop.mp3 --translation one_way
node soniox_realtime.js --audio_path ../assets/two_way_translation.mp3 --translation two_way

# Async examples
node soniox_async.js --audio_path audio-sample-1.mp3
node soniox_async.js --audio_path ../assets/florNormal.m4a
node soniox_async.js --audio_path "https://s3.ap-south-1.amazonaws.com/cs-portal-qa.nprd.innovxcare-ai.com/assets/TestCasesForSoniox/florNormal.m4a?response-content-disposition=inline&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEM%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCmFwLXNvdXRoLTEiRzBFAiEAotdN8QTr%2Fl2P8WAwNCthRVMHuEHA4wgQ52wyqoODTzgCIGw51IDMyjes028TRA%2FuOD2dYPb%2B9VkBaX5r3wv%2FEzVJKrIECFgQABoMMjIyNjM0Mzc0Nzk2IgyfXnqFozc3ac%2FLw%2BIqjwTRSDQTA5vnGvOojJIpU7%2B3h5Vw6tFx64V8bpCC6LswHD%2BtQsk8m3eRXJZlmVdVgfPoBgTyhyjLenMvaaTLuhclkM5v4cQ2Mlf9NrPL%2Bas5H1pXvd%2B49JkdHiCFWwnjF3cL5a9FMSGaClbCfb2Aat4oZ9LCiYwkiCx8zrITLHUJd7exIWQCPokjEftMd7ThXj4FYR1SSgAyesW9%2BjT7l%2B5Xo2UC4JDnN3%2F2mA0IuU09Nw8okkGwIL11eqYVMMzAjtZCA2aHh5IpBkCbHmZ0deGMh7duvRzg9LlmMsH%2BL6X6RYSANbrNasF4RiM15%2FD0ELkmQ2mwKHxUwPc1giJs84qwKfwdOgNxeaPZao8FA51t7xZMYc9jgCzJlRKkd8RTbdEnRB4QxWI6%2FYdOvBXiWqMjtEnI3I0JgFRxzue9MQjzx7tqL%2Bw87E4DxYbEMYLE1KNoisnEba9jjsti%2FbnjrvJLIXY0Y4VQE7k8LrjDxqxiZ43DWfp%2FAWGhuabgWHS3%2BVqvjRC4HjEG0O%2BVClR0em0tLP248Y4tKCWNyPrkXt2gzAO3Y1y21fFtLzpjSPjW05kx4slWgFi2R5VmXw3nZmoJqL0SXxAxjWOHC%2B34MkQrag6dVioKEse0srLCDIHMdlZi21POBFzC1Eo8LU4Hj7xr6qGhKnusqr5c6JrddVSOIBFqWHwAgKyXViHjY1qHtzC3rs7GBjrFAgFhYZfXrN%2B%2BEMTUYu%2FYu1qH5QL99kWvbMA20FQVYm6bkM7nwej43fmqqiKXJyZcIDyTHHHbIJR%2BUp64uIrXUi%2F9tjXUiBAKCSZ4ooCvTAdIaMh%2BcxI73VsiMeqOEjRLsdRLlxN2U9kNzCchlr05WBLosXio6LJ0aGqdNsvggp%2Bnb33wCWvHX%2Bu%2BaAq7FeY%2FCDFMmTtaUV04H5m%2FPteBeUbxJCv31qqCYGP89g1BUYjWPZXdu5Qc9phI8CJxdCL48Fowx%2FbfiVPL6uTQ%2FGopQ8%2FVY8fzzc8CkfV9rSdbAiAIusNfRn5frkTYxor2KDB8pWFb12S%2BEgEYU2nbivJEMuHQTzdXXc55GVydjgdNcSQZ4TuNa2n3i%2FWZS%2FzIujZePGI%2ByhkWS1PIYEcM%2FWcOtR2yWn6QLp6FhYLMSGS3xonkULmofAI%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=ASIATHVQK62GN326JBUV%2F20250924%2Fap-south-1%2Fs3%2Faws4_request&X-Amz-Date=20250924T070523Z&X-Amz-Expires=3600&X-Amz-SignedHeaders=host&X-Amz-Signature=2f57e9f5266a400eadf5f5c7304962ed067ea3ec20c9e81c16b7b1257144ecba"

node soniox_async.js --audio_url  "https://s3.ap-south-1.amazonaws.com/cs-portal-qa.nprd.innovxcare-ai.com/assets/TestCasesForSoniox/coffee_shop.mp3?response-content-disposition=inline&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEM%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCmFwLXNvdXRoLTEiRzBFAiEAotdN8QTr%2Fl2P8WAwNCthRVMHuEHA4wgQ52wyqoODTzgCIGw51IDMyjes028TRA%2FuOD2dYPb%2B9VkBaX5r3wv%2FEzVJKrIECFgQABoMMjIyNjM0Mzc0Nzk2IgyfXnqFozc3ac%2FLw%2BIqjwTRSDQTA5vnGvOojJIpU7%2B3h5Vw6tFx64V8bpCC6LswHD%2BtQsk8m3eRXJZlmVdVgfPoBgTyhyjLenMvaaTLuhclkM5v4cQ2Mlf9NrPL%2Bas5H1pXvd%2B49JkdHiCFWwnjF3cL5a9FMSGaClbCfb2Aat4oZ9LCiYwkiCx8zrITLHUJd7exIWQCPokjEftMd7ThXj4FYR1SSgAyesW9%2BjT7l%2B5Xo2UC4JDnN3%2F2mA0IuU09Nw8okkGwIL11eqYVMMzAjtZCA2aHh5IpBkCbHmZ0deGMh7duvRzg9LlmMsH%2BL6X6RYSANbrNasF4RiM15%2FD0ELkmQ2mwKHxUwPc1giJs84qwKfwdOgNxeaPZao8FA51t7xZMYc9jgCzJlRKkd8RTbdEnRB4QxWI6%2FYdOvBXiWqMjtEnI3I0JgFRxzue9MQjzx7tqL%2Bw87E4DxYbEMYLE1KNoisnEba9jjsti%2FbnjrvJLIXY0Y4VQE7k8LrjDxqxiZ43DWfp%2FAWGhuabgWHS3%2BVqvjRC4HjEG0O%2BVClR0em0tLP248Y4tKCWNyPrkXt2gzAO3Y1y21fFtLzpjSPjW05kx4slWgFi2R5VmXw3nZmoJqL0SXxAxjWOHC%2B34MkQrag6dVioKEse0srLCDIHMdlZi21POBFzC1Eo8LU4Hj7xr6qGhKnusqr5c6JrddVSOIBFqWHwAgKyXViHjY1qHtzC3rs7GBjrFAgFhYZfXrN%2B%2BEMTUYu%2FYu1qH5QL99kWvbMA20FQVYm6bkM7nwej43fmqqiKXJyZcIDyTHHHbIJR%2BUp64uIrXUi%2F9tjXUiBAKCSZ4ooCvTAdIaMh%2BcxI73VsiMeqOEjRLsdRLlxN2U9kNzCchlr05WBLosXio6LJ0aGqdNsvggp%2Bnb33wCWvHX%2Bu%2BaAq7FeY%2FCDFMmTtaUV04H5m%2FPteBeUbxJCv31qqCYGP89g1BUYjWPZXdu5Qc9phI8CJxdCL48Fowx%2FbfiVPL6uTQ%2FGopQ8%2FVY8fzzc8CkfV9rSdbAiAIusNfRn5frkTYxor2KDB8pWFb12S%2BEgEYU2nbivJEMuHQTzdXXc55GVydjgdNcSQZ4TuNa2n3i%2FWZS%2FzIujZePGI%2ByhkWS1PIYEcM%2FWcOtR2yWn6QLp6FhYLMSGS3xonkULmofAI%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=ASIATHVQK62GN326JBUV%2F20250924%2Fap-south-1%2Fs3%2Faws4_request&X-Amz-Date=20250924T070815Z&X-Amz-Expires=3600&X-Amz-SignedHeaders=host&X-Amz-Signature=bc9c0aa864196a75d0fb4c4208805163957670f5b0458bfa6bbbe50b5826e2bb"


node soniox_async.js --audio_url https://www.nch.com.au/scribe/practice/audio-sample-1.mp3
node soniox_async.js --audio_path /Users/gayathrimatcha/Downloads/PuluFirstLineMissing_report-1737564762973-1737564762424-final.wav
node soniox_async.js --audio_url "https://soniox.com/media/examples/coffee_shop.mp3"
node soniox_async.js --audio_path ../assets/coffee_shop.mp3
node soniox_async.js --delete_all_files
node soniox_async.js --delete_all_transcriptions
```
