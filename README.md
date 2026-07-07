# Launchpad

A lightweight browser-based sample rack) for [sharing collections](https://adrianartacho.github.io/launchpad/?title=Tuishi%20Pamoja&folder=pamoja) of audio samples.

Simply upload audio files to a GitHub repository, enable GitHub Pages, and share a URL. Visitors can trigger samples directly from their browser without installing Ableton Live or any other software.

## Features

* Automatic generation of pads from files stored in a repository
* Support for WAV, MP3, OGG, M4A, FLAC and AIFF files
* Dynamic titles via URL parameters
* Multiple sample banks via subfolders
* Full-screen mode on first interaction
* "Stop All" button to immediately stop all currently playing samples
* Mobile-friendly interface
* Zero dependencies

## Installation

Create the following repository structure:

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

### Folder

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

The application discovers samples through the GitHub API. Therefore:

* The repository must be public.
* Sample names become pad labels.
* New files appear automatically after committing them to the repository.

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

## [ToDo](https://trello.com/c/0g6VE3OI/266-launchpad)

