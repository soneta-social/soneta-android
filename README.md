## Soneta for Android

[Soneta](https://soneta.social) is an open-source social network built on Telegram's open-source client code.
This repo contains the official source code for [Soneta for Android](https://play.google.com/store/apps/details?id=social.soneta.network).

## Creating your own Soneta-based application

We welcome all developers to build on Soneta's open-source code, the same way Soneta itself was built on Telegram's. There are a few things we require from **all developers** who fork or redistribute this code:

1. [**Obtain your own api_id**](https://core.telegram.org/api/obtaining_api_id) - Soneta connects to Telegram's network via the Telegram API, and so does any app built on this code. Do not reuse Soneta's own credentials.
2. Please **do not** use the name soneta for your app — or make sure your users clearly understand that it is an unofficial fork.
3. Kindly **do not** Soneta's logo or visual identity as your app's own branding. 
4. Please study Telegram's [**security guidelines**](https://core.telegram.org/mtproto/security_guidelines) and take good care of your users' data and privacy.
5. Please publish **your** code too, in order to comply with the license terms of both Soneta's own code and the underlying Telegram code it's derived from.

### API, protocol documentation

Telegram API manuals: https://core.telegram.org/api

MTProto protocol manuals: https://core.telegram.org/mtproto

### Compilation guide

**Note**: in order to support [reproducible builds](https://core.telegram.org/reproducible-builds), this repo contains dummy release.keystore,  google-services.json, and filled placeholder variables inside BuildVars.java. Before publishing your own APKs, make sure to replace all of these with your own.

You will need Android Studio 3.4, Android NDK rev. 20 and Android SDK 8.1.

1. Download the Soneta source code from https://github.com/soneta-social/soneta-android ( git clone https://github.com/soneta-social/soneta-android.git )
2. Copy your release.keystore into TMessagesProj/config
3. Fill out RELEASE_KEY_PASSWORD, RELEASE_KEY_ALIAS, RELEASE_STORE_PASSWORD in gradle.properties to access your release.keystore
4. Go to https://console.firebase.google.com/, create two android apps with application ids social.soneta.network and social.soneta.network.beta, turn on firebase messaging and download google-services.json, which should be copied to the same folder as TMessagesProj.
5. Open the project in Android Studio (note: it should be opened, not imported).
6. Fill out values in TMessagesProj/src/main/java/.../buildvars.java – there’s a link for each of the variables showing where and which data to obtain.
7. you are ready to compile Soneta.

### localization

we moved all translations to https://translations.telegram.org/en/android/. please use it.
