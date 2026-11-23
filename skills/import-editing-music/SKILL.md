---
name: import-editing-music
description: >-
  Finds the requested recording by song title and artist, saves the audio in the current video's 背景音乐 folder, and imports it into the open video-editor project. Use for 剪映, CapCut, or another accessible video editor when the user asks to import or find background music, or gives a title and artist in an active video-editing context.
---

# Find and import background music

The user can provide just a song title and artist, for example `O — ML Buch`. Use the active video editor and project context to resolve the rest. For multiple tracks, save them in the same project music folder and verify each import.

## Identify the project and music folder

1. If the user asks only to find a track or provides an explicit destination folder, follow that scope. When they ask to import into an editor, inspect the open editor and identify the current project. Prefer a dedicated editor integration when it can import media. Otherwise use the supported computer-use interface. Read the project name and locate one or more source videos via the media bin, file properties, or the editor's Reveal in Finder or Explorer action.
2. Use the directory the user's project videos came from. The user's explicit folder or the established project directory takes precedence. If videos are in day or camera subfolders under a clear project directory, use that project directory. Ask a short question if several plausible projects or unrelated source folders remain and the context cannot distinguish them.
3. Use a single `背景音乐` subfolder in that directory. For example, if videos came from `桌面/日本`, save audio to `桌面/日本/背景音乐`. The editing application's internal draft directory is distinct from the source video directory. Read or create the music folder even when search and verification run elsewhere.

## Find the recording and verify the file

Start by checking the project music folder and any files the user supplied. Use the exact title and artist as search terms. For a short or common title like `O` or `Weather`, compare plausible official listings by artist, release, and duration. Use the project or a supplied link to identify the recording. If multiple plausible matches remain, show the closest candidates and ask for the artist or a listening link before saving or importing one.

### 1. Check the label's official release page for a public MP3

Find the official album or single page and match the track against the release's track list. Check the download link or the public audio player source for a file served directly by the label. Confirm that it is the full recording and is available without passing a login, purchase, or DRM restriction. A label page may host the audio on its own CDN or a CDN it uses for the release.

### 2. Search GitHub for a public MP3

Search across repositories for the exact title and artist, alternate spellings and scripts, and plausible filenames such as `Title - Artist.mp3` or `Artist - Title.mp3`. Check relevant repositories' file trees, releases, and GitHub Pages assets. Open a credible candidate and check whether the repository contains audio or points to an authorized download. Verify the host and track before accepting it. Playlists, Gists, and datasets can help identify a release, and a generic filename such as `iu.mp3` still needs duration and identity checks.

### 3. Search in a browser for a public MP3

Try the original title and its alternate or translated title with the artist, album, label, and terms such as `MP3`, `download`, or the local-language equivalent. Open promising results and verify the source and actual download option. Check artist storefronts and label-linked pages as well as web search results. An official listening page or embedded player may provide only a stream or a preview. If the confirmed download requires purchase or the user's credentials, give the exact track or release page and state what is needed. Never bypass DRM, login, or purchase controls.

### Validate and save

- Check the file opens as audio with `afinfo` on macOS or `ffprobe` where available. Compare the duration with an official listing and use the source track list or embedded metadata to match artist, title, and version. Treat mismatches as unresolved until corroborated. A store listing, playlist entry, streaming link, preview, or an app-only offline file such as NCM does not count as an editable audio file.
- Save the verified recording as `歌名 - 歌手.扩展名` under `背景音乐`, replacing any path separators in the name. Reuse the same verified file if present. If that name already holds different content, keep it and give the new file a version label. Import from the final path when the user asks to import into an editor. For a track already linked elsewhere, use the editor's relink feature if available. If you cannot safely relink, preserve the working reference and report it.
- If a direct download fails, try the official download entry or the computer's existing network configuration. If no usable file is verified, report the best confirmed source and the unresolved step.

### Examples from prior searches

- **ML Buch, `O`.** Find the exact track (no. 4) on [Anyines' official `Skinned` page](https://anyines.com/skinned/), follow the label's publicly served MP3, and verify the result as an MP3 of about 1:14 before saving it.
- **IU, `복숭아 (Peach)`.** Search in both Korean and English. A GitHub project listed the title and contained an `iu.mp3`, but audio inspection measured 4:13 versus the official track's 3:12. A Gist was a playlist record. The browser search confirmed [Qobuz](https://www.qobuz.com/us-en/album/the-spring-of-twenty-iu/g464oclsn75bc) as a paid standalone download.
- **Rook1e, `eden.`.** Search the punctuated title and artist together. GitHub turned up playlist and dataset entries. The artist's [SoundCloud track](https://soundcloud.com/byrook1e/eden) was about 1:15 and had downloads disabled. The [Bandcamp track](https://rook1e.bandcamp.com/track/eden-outro) appeared as `eden . [outro.]` and pointed to an album purchase. These pages established the recording and download options without yielding a local audio file.
- **Novo Amor, `Weather`.** Match the 3:52 original on the artist's official release page. Use the [BIRP May 2014 playlist](https://birp.fm/playlist/2014/may-2014) to identify the historical MP3, then retrieve its [single entry from the archived release](https://archive.org/details/birp-conservation-repository). The archive documents the original artist-approved free distribution. Verify the extracted file's title, artist, and duration before saving.

## Import and verify

1. Import the audio into the active project's local media bin using the editor's normal import action. Reuse any entry already backed by the same file. Place music on the timeline only if the user requests placement. Use the requested position or the project start when the user asks to add it as background music without a position.
2. In CapCut desktop on macOS, use `素材 → 我的 → 导入` or `文件 → 导入`. In the native picker, open Go to Folder with Command-Shift-G and navigate to the saved path. Confirm that the correct file is selected and the Import button is enabled. If navigation highlighted a file but the button is disabled, trigger a fresh selection with a click or arrow keys, then recheck. Test a supported PCM WAV version if the original format is rejected. Keep the version linked by the editor in `背景音乐` and keep temporary conversions outside the project.
3. Verify that the expected filename and audio duration or waveform appear in that project's media bin. If timeline placement was requested, verify the track and start time as well. Report the project name, music folder and filename, and source link. If the editor remains inaccessible, report the completed local download and the specific import blocker.

Keep the downloaded audio in the user's project media folder. A repository used to share this skill contains the instructions and supporting workflow files only.
