# external_path

external_path is a flutter plugin that provides internal, external storage path and external public storage path.
external_path also gives you the option to get the external SDCard path and all external USB storage paths (if available)

<https://pub.dev/packages/external_path>

## Features

`ExternalPath.getExternalStoragePublicDirectory()` needs Public Directory Type argument
Below given table contains the types of argument you can pass to `getExternalStoragePublicDirectory()` function

| ExternalPath                         |
| ------------------------------------ |
| ExternalPath.DIRECTORY_MUSIC         |
| ExternalPath.DIRECTORY_PODCASTS      |
| ExternalPath.DIRECTORY_RINGTONES     |
| ExternalPath.DIRECTORY_ALARMS        |
| ExternalPath.DIRECTORY_NOTIFICATIONS |
| ExternalPath.DIRECTORY_PICTURES      |
| ExternalPath.DIRECTORY_MOVIES        |
| ExternalPath.DIRECTORY_DOWNLOADS     |
| ExternalPath.DIRECTORY_DCIM          |
| ExternalPath.DIRECTORY_DOCUMENTS     |
| ExternalPath.DIRECTORY_SCREENSHOTS   |
| ExternalPath.DIRECTORY_AUDIOBOOKS    |

## Usage

First Add `external_path` as a dependency in your project `pubspec.yaml`.

Then, import `external_path` package.

```dart
import 'package:external_path/external_path.dart';
```

Package has four functions

```dart
  // Get storage directory paths
  Future<void> printExternalStoragePaths() async {
    var path = await ExternalPath.getExternalStorageDirectories();
    print(path);  // [/storage/emulated/0, /storage/B3AE-4D28]

    // please note: B3AE-4D28 is external storage (SD card) folder name it can be any.
  }


  // To get public storage directory path
  Future<void> printPublicDownloadsDirectoryPath() async {
    var path = await getExternalStoragePublicDirectory(ExternalPath.DIRECTORY_DOWNLOADS);
    print(path);  // /storage/emulated/0/Download
  }


  // Get SDCard storage directory path
  Future<void> printSDCardPath() async {
    var path = await getSDCardStorageDirectory();
    print(path);  // /storage/B3AE-4D28 (example value)
  }


  // Get USB storage directory paths
  Future<void> printUSBStoragePathss() async {
    var path = await getUSBStorageDirectories();
    print(path);  // /storage/F403-1AD0 (example value)
  }
```
