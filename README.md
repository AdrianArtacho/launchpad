# Launchpad

A lightweight browser-based sample rack for [sharing collections](https://adrianartacho.github.io/launchpad/?title=Tuishi%20Pamoja&folder=pamoja) of audio samples.

Store audio in a link-shared Google Drive folder or a public GitHub repository, then share one Launchpad URL. Visitors do not need to install Ableton Live or sign in to Google.

[→helper](https://adrianartacho.github.io/launchpad/helper.html)

## Features

* Automatic generation of pads from a Google Drive folder or a GitHub repository
* Support for WAV, MP3, OGG, M4A, FLAC and AIFF files
* Dynamic titles via URL parameters
* Multiple sample banks via subfolders
* Full-screen mode on first interaction
* "Stop All" button to immediately stop all currently playing samples
* Mobile-friendly interface
* Zero dependencies

## Share audio from Google Drive

1. Put the audio files in a dedicated Drive folder. In **Share → General access**, choose **Anyone with the link → Viewer**. Anyone who receives the link can access the files; this is link sharing, not access restricted to named people.
2. In [Google Cloud](https://console.cloud.google.com/apis/library/drive.googleapis.com), enable the **Google Drive API** for a project and [create an API key](https://console.cloud.google.com/apis/credentials). Restrict the key to **Websites** (`https://adrianartacho.github.io` and `https://adrianartacho.github.io/*`) and to the **Google Drive API**. This is a browser key for public data, not an OAuth token or a credential for your private Drive.
3. Open the [URL helper](https://adrianartacho.github.io/launchpad/helper.html), select **Google Drive folder**, and paste the folder sharing link and API key. Add a title if you like, then copy the generated Launchpad URL.

The API key is included in the shared Launchpad URL so visitors can list that folder without logging in. Keep its website and API restrictions enabled. Newly added audio files appear when the page is reloaded. The folder URL and its file IDs are never stored in this repository by this feature.

Google Drive's own viewer can play the files if a browser cannot play one inside Launchpad; the pad will offer a link to open that file in Drive. The Drive API is also subject to Google's quotas.

## GitHub audio sources

To use the original GitHub source, create the following repository structure:

```text
launchpad/
├── index.html
└── samples/
    ├── kick.wav
    ├── snare.wav
    └── ...
```

Additional sample banks can be placed in subfolders:

```text
samples/
├── drumkit/
│   ├── kick.wav
│   └── snare.wav
├── panoja/
│   ├── sample1.wav
│   └── sample2.wav
└── ...
```

Enable GitHub Pages:

```text
Settings → Pages → Deploy from branch
```

Choose:

```text
Branch: main
Folder: / (root)
```

The application will be available at:

```text
https://YOUR_USERNAME.github.io/launchpad/
```

## URL Parameters

The [helper](https://adrianartacho.github.io/launchpad/helper.html) builds these URLs for you.

### Google Drive folder

`?drive=DRIVE_FOLDER_URL&driveKey=RESTRICTED_BROWSER_API_KEY` loads audio files from a link-shared Drive folder. `drive` and `repo` are mutually exclusive. The folder link should have the form `https://drive.google.com/drive/folders/FOLDER_ID` (including `resourcekey` if Google supplied one).

The Drive API key is visible to anyone with the shared URL; restrict it to the Google Drive API and the Launchpad website before sharing.

### Title

Sets the page title and header.

```text
?title=My%20Sample%20Pack
```

Example:

```text
https://YOUR_USERNAME.github.io/launchpad/?title=My%20Sample%20Pack
```

---

### GitHub folder

Loads samples from a specific subfolder inside `samples/`.

```text
?folder=panoja
```

This will load:

```text
samples/panoja/
```

Example:

```text
https://YOUR_USERNAME.github.io/launchpad/?folder=panoja
```

---

### Combined Example

```text
https://YOUR_USERNAME.github.io/launchpad/?title=Panoja&folder=panoja
```

## Usage

Click any pad to trigger its corresponding sample.

The interface enters full-screen mode on first interaction (subject to browser permissions).

Use the **Stop All** button to immediately stop all currently playing sounds.

## Notes

For GitHub sources, the application discovers samples through the GitHub API. Therefore:

* The repository must be public.
* Sample names become pad labels.
* New files appear automatically after committing them to the repository.

For Drive sources, the folder must allow "Anyone with the link" access. A folder sharing link does not prevent a recipient from forwarding it. Do not disable downloading if you want the browser to play the audio.

## Potential Applications

* Drum kits
* Sound libraries
* Theatre cue collections
* Foley libraries
* Educational listening exercises
* Instrument demonstrations
* Artistic portfolios
* Interactive sound installations

## License

MIT License

---

## 📝[ToDo](https://trello.com/c/0g6VE3OI/266-launchpad)
