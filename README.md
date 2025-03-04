<!--
  Copyright 2020-2021 Ayogo Health Inc.

  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

      https://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
-->

# cordova-plugin-update-notifier

This plugin provides a mechanism for showing an in-app notification when a new
version of the app is available for download from the App Store.

For iOS, this uses the [Siren][siren] library.

## Installation

### Cordova

```
cordova plugin add cordova-plugin-update-notifier
```

### Capacitor

```
npm install cordova-plugin-update-notifier
npx cap sync
```

## Configuration Preferences

### Alert Type

Siren's implementation for iOS allows for different alert types (see https://github.com/ArtSabintsev/Siren#screenshots). You can set the value to "critical" or "annoying" in config.xml.

```xml
<preference name="SirenAlertType" value="critical" />
<preference name="SirenAlertType" value="annoying" />
```

### Non US-AppStore iOS apps

Siren's implementation for iOS requires specifying a country code if your app is not published to the US AppStore.

```xml
<preference name="SirenCountryCode" value="CA" />
```

For Capacitor, add `"SirenCountryCode": "CA"` to your capacitor.config.json file.

### Managed App Configuration

When deploying an app using an MDM, you can take advantage of [Managed App Configuration](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) to disable the update check. Simply create a preference called "DisableUpdateCheck" and set it's value to "true".

## Supported Platforms

-   **Cordova CLI** (cordova-cli >= 9.0.0)
-   **iOS** (cordova-ios >= 5.0.0, or capacitor)

## Contributing

Contributions of bug reports, feature requests, and pull requests are greatly
appreciated!

Please note that this project is released with a [Contributor Code of
Conduct][coc]. By participating in this project you agree to abide by its
terms.

## Licence

Released under the Apache 2.0 Licence.
Copyright © 2020-2021 Ayogo Health Inc.

[siren]: https://sabintsev.com/Siren/
[coc]: https://github.com/AyogoHealth/cordova-plugin-update-notifier/blob/main/CODE_OF_CONDUCT.md
