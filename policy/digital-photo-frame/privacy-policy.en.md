# Digital Photo Frame Privacy Policy

- App: Digital Photo Frame / 디지털액자
- Developer: PSH4607 (박성호)
- Contact: [dev.psh30095@gmail.com](mailto:dev.psh30095@gmail.com)
- Revision and effective date: October 9, 2026

This policy explains how PSH4607 handles photos and settings in Digital Photo Frame. It covers the Android app's photo playback features and inquiries sent directly to the developer.

Photo handling depends on the installed app version. The existing 0.1.x version with a single photo list reads original device-album URIs and refreshes the list when you return to the app or start the frame. Versions with named app albums copy newly imported photos into internal storage cumulatively, without automatic synchronization. Descriptions of app album creation, photo removal, and album deletion below apply to versions with those features. Publishing this policy does not itself mean that an app update has been released.

## 1. Information processed on your device

The app does not require an account or sign-in. It processes the following information on your device to display your photos.

| Information | Purpose and storage |
| --- | --- |
| Photos you select through the system photo picker | Copied to the app's private internal storage for offline playback. |
| Device photos and album information you allow the app to access | Used to display device albums and photo counts. Versions with app albums copy selected device-album photos to private internal app storage at import time without automatic synchronization. The existing single-list version references originals and refreshes its list. |
| Photo paths or URIs, source URIs for duplicate detection, app album identifiers and names, and the default and last played album | Stored in private internal app storage to restore each album and prevent the same source URI from being added twice to the same app album. |
| Display interval, sequential or shuffle mode, per-album playback order and position, and whether the usage hint has been shown | Stored in private internal app storage to restore shared settings and per-album playback state. |

Picker imports and device-album imports in versions with app albums copy the contents of the original file. Embedded metadata, such as capture time or location, may therefore remain in the imported copy. The app does not separately extract this metadata to track or analyze your location. It uses the device media store's capture-date information to sort album photos.

## 2. Photo permissions

The photo picker option uses the Android system photo picker. The direct photo selection and Google Photos selection options in earlier versions use the same system picker. The app imports the items you select.

Choosing a device album requests photo or storage read access, depending on your Android version. On Android 14 or later, if you grant access to selected photos only, the app lists device albums and imports photos within that permitted selection. Later additions to or deletions from the original album are not automatically reflected in the imported app album.

You can change or revoke photo permissions in your device settings. You can use the system photo picker without granting broad photo access. Revoking permission may prevent further device-album queries and imports, or playback of original photo references used by the existing version or retained during an update, but it does not automatically delete copies already imported into the app.

When updating from an earlier version, existing photos and playback state are migrated into an app album. Photos previously stored as original device-album URIs may retain those references to avoid data loss. These photos are not automatically synchronized, and deleting originals or changing permissions may make them unavailable for playback. Newly imported photos use internal copies.

## 3. Transfers and third-party services

The current app does not send photos or playback settings to a developer-operated server. It does not use advertising, user behavior analytics, or a separate crash-reporting SDK, and it does not declare internet access permission. It has no feature for sharing or selling your photos to external parties.

Selection and download of cloud photos, including Google Photos, depend on the system photo picker and photo provider connected to your device. The app does not receive your Google account password or authentication token, and does not directly synchronize Google Photos albums. Your use of a photo provider's service is subject to that provider's privacy policy.

Information processed by Google's own services, such as Google Play distribution, purchases, and device diagnostics, is governed by the [Google Privacy Policy](https://policies.google.com/privacy). Those services are separate from processing performed directly by this app.

This privacy policy website is hosted on GitHub Pages and uses no advertising or analytics scripts of its own. Hosting information, such as visitors' IP addresses, may be processed under the [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement). Photos stored in the app are not transmitted to this website.

## 4. Retention and deletion

Imported photos and settings remain on your device to provide the app's features. They do not expire automatically after a fixed period.

The existing single-list version attempts to remove unused internal copies after successfully replacing the photo list or source.

In versions with app albums, imports add photos to the selected app album without replacing its existing contents. Cancellation or import failure leaves the existing album contents intact. You can remove selected photos or delete an app album within the app. After saving those changes, the app attempts to remove internal photo copies no longer referenced by any app album. Photos used by other app albums are retained. Unused copies may remain after a save failure, unexpected shutdown, or unsuccessful file deletion.

To remove all imported photos and settings, use **Storage → Clear storage / Clear data** for this app in Android settings, or uninstall the app. Menu names vary by device. **Clearing the cache alone does not remove all imported photos and settings.** The current app does not have an in-app delete-all button.

Clearing app data or uninstalling the app does not delete originals in your device gallery or cloud photo service. Deleting an original from your gallery or cloud service does not remove a copy previously imported into the app; delete that copy separately using the methods above.

The developer cannot remotely access or delete photos and settings stored on your device. There is no app account to close.

## 5. Data protection

Photo copies and settings are stored in internal app storage protected by Android's app access controls. The app provides no cloud backup or account synchronization feature and is configured to disable Android automatic backup. Device migration features provided by your device manufacturer are subject to the device's settings and policies.

## 6. Contact and your choices

You can send privacy inquiries to [dev.psh30095@gmail.com](mailto:dev.psh30095@gmail.com). If you contact us, your sender email address, message, and any attachments you choose to provide are delivered by email. We use Gmail to respond to inquiries, so the email service also processes that correspondence. You do not need to send sensitive photos, identity documents, or other material unnecessary for your inquiry.

Correspondence is used to respond to your inquiry and handle your request. It is separate from photos and settings processed locally by the app. Support emails and attachments are deleted within 90 days after the inquiry is closed.

You can change permissions and delete app data through device settings. You can also contact the privacy email address to request access to, correction of, or deletion of information you provided directly in correspondence.

## 7. Changes to this policy

If the app's data handling changes, we will update this policy and any necessary in-app notices, identifying the revision and effective dates.
