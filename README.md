# Play library
<p align="center">
  <img src="https://user-images.githubusercontent.com/82513502/173231252-9d9b1090-edf4-474d-9837-831a66277145.png" width="350px">
</p>
<h2 align="center">Fast, Enjoyable & Customizable Play library</h2>

[![Pub Version](https://img.shields.io/pub/v/play?label=pub.dev&labelColor=333940&logo=dart)](https://pub.dev/packages/play)

Play Library untuk memutar video dan audio cross platform dengan mudah hanya menambah code pada dart, example sudah ada di

## Features

- 🚀 Cross platform: mobile, desktop
- ⚡ Great performance
- ❤️ Simple, powerful, & intuitive API

---

## Demo


https://user-images.githubusercontent.com/82513502/204106088-90c8d756-fbee-4724-9087-46bc99e69a00.mp4

https://user-images.githubusercontent.com/82513502/204106197-4bc3d9ba-f374-40ff-9913-7f4ffd40b530.mp4



## Install Library
```bash
dart pub add play
```

```bash
flutter pub add play
```

- [Doc + Example](https://github.com/azkadev/play)
- [Youtube-Tutorial](https://youtube.com/@azkadev)

## To-Do

1. [x] Cross platform support (Android,iOS,Linux, Windows)
2. [x] Easy Play Video and Audio
3. [x] Custom View Audio And Video
4. [ ] Realtime Player Like (call, streaming)
5. [ ] Custom Encoding & Decoding Audio & Video
 
## Quickstart

add library in first dart file

```dart
import 'package:play/play.dart';
```

add this in main function
```dart

void main() async {
  ---
  await playInitialize();
  --- 
}
```

Audio Player
```dart

Scaffold(

  ---
  Audio(
    audioData: AudioData.file(
      file: File(path),
    ),
    isAutoStart: false,
    builder: (BuildContext context, Widget child, Audio audio, AudioState audioState,AudioController audioController) {
      return child;
    }
  );
  ---

)
```

Video Player
```dart
Scaffold(

  ---
  Video(
    videoData: VideoData.file(
      file: File(path),
    ),
    isAutoStart: false,
    builder: (BuildContext context, Widget child, Video video, VideoState videoState, VideoController videoController) {
      return child;
    }
  );
  ---

)
```
If there is an error like this
```dart
Because no versions of file_picker match >5.2.3 <6.0.0 and file_picker 5.2.3 depends on ffi ^2.0.1, file_picker ^5.2.3 requires ffi ^2.0.1.
Because dart_vlc_ffi 0.1.8 depends on ffi ^1.0.0 and no versions of dart_vlc_ffi match >=0.1.7 <0.1.8-∞ or >0.1.8 <0.2.0, dart_vlc_ffi ^0.1.7 requires ffi ^1.0.0.
Thus, file_picker ^5.2.3 is incompatible with dart_vlc_ffi ^0.1.7.
And because dart_vlc 0.3.0 depends on dart_vlc_ffi ^0.1.7, file_picker ^5.2.3 is incompatible with dart_vlc 0.3.0.
Because every version of play from path depends on dart_vlc ^0.3.0 and no versions of dart_vlc match >0.3.0 <0.4.0, every version of play from path requires dart_vlc 0.3.0.
Thus, file_picker ^5.2.3 is incompatible with play from path.
So, because example depends on both play from path and file_picker ^5.2.3, version solving failed.
pub get failed (1; So, because example depends on both play from path and file_picker ^5.2.3, version solving failed.)
```
add the library that the example needs in pubspec.yaml
<!-- Thank you for [lsdlh](https://github.com/lsdlh) [Issue](https://github.com/azkadev/play/issues/2) -->
```yaml 
---
dependency_overrides:
  ffi: 2.0.1
---
```

> I don't have enough native coding skills so I can't add many features in this library, if you want to contribute please just add it I'll be happy if you help me


## Docs
I use 3 libraries so your document can be seen here

1. [audioplayers](https://github.com/bluefireteam/audioplayers)
2. [video_player](https://github.com/flutter/plugins/tree/main/packages/video_player/video_player)
3. [dart_vlc](https://github.com/alexmercerind/dart_vlc)


### Audio
Documentation audio

1. AudioData
   
  - file
    ```dart
    AudioData.file(
      file: File("./path_to_audio.mp3"),
    )
    ```
  - asset
    ```dart
    AudioData.asset(
      asset: "assets/audio/audio.mp3",
    )
    ```
  - network
    ```dart
    AudioData.network(
      url: "https://example.com/example.mp3",
    )
    ```

2. isAutoStart 
   - `true`
      if you want auto play set data to true
   - `false`
      if you don't want auto play set data to true
3. id
   - int
    If you want to play a lot of media, add the IDs in the order of the videos / don't have the same ones

4. builder

#### AudioController
- `pause`
- `play`

### Video
Documentation video
```dart

Scaffold(
  child: Video(
    videoData: VideoData.file(
      file: File(path),
    ),
    isAutoStart: false,
    builder: (BuildContext context, Widget child, Video video, VideoState videoState, VideoController videoController) {
      /// custom view
      return child;
    }
  );
)
```

1. videoData
   
  - file
    ```dart
    VideoData.file(
      file: File("./path_to_video.mp4"),
    )
    ```
  - asset
    ```dart
    VideoData.asset(
      asset: "assets/videos/video.mp4",
    )
    ```
  - network
    ```dart
    VideoData.network(
      url: "https://example.com/example.mp4",
    )
    ```
2. isAutoStart 
   - `true`
      if you want auto play set data to true
   - `false`
      if you don't want auto play set data to true
3. id
   - int
    If you want to play a lot of media, add the IDs in the order of the videos / don't have the same ones

4. builder

#### VideoController
- `seek(Duration())`
- `playOrPause`
- `isPlaying`
- `pause`
- `play`
- `size`
- `aspectRatio`
- `setPlaybackSpeed(1.5)`
- `setVolume(0.5)`