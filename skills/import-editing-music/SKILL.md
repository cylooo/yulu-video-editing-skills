---
name: import-editing-music
description: >-
  Finds the requested recording by song title and artist, saves the audio in the current video's 背景音乐 folder, and imports it into the open video-editor project. Use for 剪映, CapCut, or another accessible video editor when the user asks to import or find background music, or gives a title and artist in an active video-editing context.
---

# Find and import background music

The user can provide just a song title and artist, for example `O — ML Buch`. Use the active video editor and project context to resolve the rest. For multiple tracks, save them in the same project music folder and verify each import.

## Identify the project and music folder

1. Inspect the open editor and identify the current project. Prefer a dedicated editor integration when it can import media. Otherwise use the supported computer-use interface. Read the project name and locate one or more source videos via the media bin, file properties, or the editor's Reveal in Finder or Explorer action.
2. Use the directory the user's project videos came from. The user's explicit folder or the established project directory takes precedence. If videos are in day or camera subfolders under a clear project directory, use that project directory. Ask a short question if several plausible projects or unrelated source folders remain and the context cannot distinguish them.
3. Use a single `背景音乐` subfolder in that directory. For example, if videos came from `桌面/日本`, save audio to `桌面/日本/背景音乐`. The editing application's internal draft directory is distinct from the source video directory. Read or create the music folder even when search and verification run elsewhere.

## Find and verify the recording

1. Look for an existing matching file in `背景音乐` and user-provided media. Search using the title and artist together. For names like `O`, corroborate the artist, album or release, and duration using primary sources such as the artist, label, or official listing. Use the main release by default and honor any version the user specifies.
2. Look for an actual importable file from the artist, label, or authorized service. Examples include a user-owned download, a label's publicly served direct audio file for the exact track, and an authorized digital download. A preview clip, a store page, and a misleading editor-library search result each require further verification. If the full recording requires purchase or credentials held by the user, give the exact source and explain what is needed to resume. Never bypass DRM, login, or purchase controls.
3. Verify that the file opens as audio and that its duration matches the release within normal rounding. Use format inspection such as `afinfo` on macOS or `ffprobe` when available. Corroborate identity with the source's track listing or embedded artist and title. If a direct download fails, try the official download entry or the computer's existing network configuration.
4. Save the verified media as `歌名 - 歌手.扩展名` under `背景音乐`, replacing any path separators in the name. Reuse the same verified recording if it already exists. If the destination name holds different content, retain it and give the new file a version label. Import from this final path so the project can reopen it later. For a track already linked elsewhere, use the editor's relink feature when available. If you cannot safely relink, preserve the working reference and report it.

## Import and verify

1. Import the audio into the active project's local media bin using the editor's normal import action. Reuse any entry already backed by the same file. Place music on the timeline only if the user requests placement. Use the requested position or the project start when the user asks to add it as background music without a position.
2. In CapCut desktop on macOS, use `素材 → 我的 → 导入` or `文件 → 导入`. In the native picker, open Go to Folder with Command-Shift-G and navigate to the saved path. Confirm that the correct file is selected and the Import button is enabled. If navigation highlighted a file but the button is disabled, trigger a fresh selection with a click or arrow keys, then recheck. Test a supported PCM WAV version if the original format is rejected. Keep the version linked by the editor in `背景音乐` and keep temporary conversions outside the project.
3. Verify that the expected filename and audio duration or waveform appear in that project's media bin. If timeline placement was requested, verify the track and start time as well. Report the project name, music folder and filename, and source link. If the editor remains inaccessible, report the completed local download and the specific import blocker.

Keep the downloaded audio in the user's project media folder. A repository used to share this skill contains the instructions and supporting workflow files only.
