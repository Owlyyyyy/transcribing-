# Gemini Batch Transcriber

Batch audio transcription desktop app powered by Google's Gemini API and Python Tkinter.

## Features

- Select and transcribe multiple audio files in one batch
- Enter a Gemini API key through the GUI, with a show/hide toggle
- Pick any output folder for `_raw.txt` transcripts
- Request speaker diarization (Speaker 1, Speaker 2, etc.)
- Follow live progress and errors without freezing the UI
- Avoid overwriting existing transcripts

## Requirements

Python 3.10+ (with Tkinter) and an API key with access to the configured Gemini transcription model.

## Setup (Windows PowerShell)

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python transcribe_gui.py
```

Or run `run_windows.bat` after installing dependencies into `.venv`.

## How to use

1. Paste your API key in the Gemini API key field.
2. Click **Add audio files** to select multiple recordings.
3. Choose an output directory with **Browse...**
4. Click **Start transcription**.

Each recording is saved as `<audio-name>_raw.txt`. If that name is already taken, a numeric suffix is used.

## API key safety

The app holds your API key in memory only; it is not written to disk. `.gitignore` excludes common secret files, recordings, and generated transcripts. Review changes before committing.

Recordings are uploaded to Google's servers for transcription. Check the data handling terms applicable to your API account.

## Testing

```powershell
python -m unittest discover -s tests -v
```

## License

No open-source license has been selected yet.
