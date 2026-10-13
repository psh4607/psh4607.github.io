# Digital Photo Frame Privacy Policy

- App: Digital Photo Frame / 디지털액자
- Developer: PSH4607 (박성호)
- Contact: [dev.psh30095@gmail.com](mailto:dev.psh30095@gmail.com)
- Revision and effective date: October 13, 2026

This policy explains how PSH4607 handles photos and settings in Digital Photo Frame. It covers the Android app's photo playback features and inquiries sent directly to the developer.

You can identify photo handling by the app’s album management screen. The legacy app, which has no screen for creating or managing named app albums and lets you select only one photo list, reads original device-album URIs and refreshes the list when you return to the app or start the frame. Manual albums in an app with a screen for creating and managing named app albums copy newly imported photos into internal storage cumulatively, without automatic synchronization. Descriptions of app album creation, photo removal, and album deletion below apply to apps with that album management screen. Development builds may display the same version number, so the version number alone does not distinguish these behaviors. Publishing this policy does not itself mean that an app update has been released.

## Device gallery album linking (feature under development)

The following applies only to builds with the “Link a gallery album” feature. It differs from manual imports in existing installations; publishing this policy does not establish a feature release.

Link targets are folder-based albums on the same device where the app is installed and, on Android 11 or later, photos marked as favorites in the system media store (MediaStore). Favorites collect photos on that device using favorite information shared with the system; an empty favorites collection can remain linked and reflect later changes. Favorites kept privately by a gallery app or managed only in the cloud without being shared with the system, people categories, and albums on other devices are not targets. The app stores the linked album’s storage volume and album (bucket or favorites collection) identifiers, name and path, original photo content URIs, and link and playback state in private internal app storage. Linked photos are read from originals without creating internal photo copies.

Linking requires full photo read access. Selected-photo access or denial prevents completing a link. When another system request is available, the app requests access again in response to your action; otherwise it directs you to device settings. If access is revoked or reduced to selected photos after linking, the app preserves the link and existing list and pauses linked-photo playback. It queries again after full access is restored.

The app refreshes the linked folder or system favorites collection when you open the app or start playback, and when device photo changes are detected during playback. This one-way link reflects photo additions and deletions and system favorite selections and removals in the frame list without modifying or deleting gallery originals. Insufficient permission or a query error alone does not delete the link or existing list. Deleting a linked album removes only its app link information, photo list, and playback state.

Long-pressing a linked album and choosing “Unlink album” copies the photos currently in that album to private internal app storage, then converts the same album to a manual album. After conversion, additions and deletions in the original album are no longer reflected automatically; gallery originals are not modified or deleted. The link remains until every photo has been copied and album storage is committed. If copying or saving fails, or you cancel during copying, the existing link and photo list are preserved and temporary copies created by the operation are cleaned up. Successfully converted internal copies follow the retention and deletion behavior below.

Internal copies imported into manual albums retain the existing retention and deletion behavior. Direct Google Photos Picker imports are also unchanged. Google Photos Ambient API integration awaits partner approval and is not provided; screens marked awaiting approval or coming soon do not request access or retrieve data for that feature.

## 1. Information processed on your device

No app account or registration is required. Playing device photos does not require sign-in; choosing to import from Google Photos requires Google account authorization and consent. The app processes the following information on your device.

| Information | Purpose and storage |
| --- | --- |
| Photos you select from the device gallery, system photo picker, or Google Photos selection screen | Copied to private internal app storage for offline frame playback. Google Photos imports download only your selected photos; videos are not imported. |
| Device photos and album information you permit the app to access | Used to display permitted gallery photos, albums, and photo counts and let you select photos. On Android 11 or later, the system’s favorite information is read to construct the linked list. The legacy single-list version references originals and refreshes its list. |
| Photo paths or URIs, source URIs or Google Photos media identifiers for duplicate detection, app album identifiers and names, and the default and last played album | Stored in private internal app storage to restore each album and prevent the same source from being added twice to the same app album. |
| Display interval, sequential or shuffle mode, photo size/display mode (Fit, Fill, or Stretch), per-album playback order and position, and legacy usage-hint state | Stored in private internal app storage to restore shared settings and per-album playback state. The legacy hint value is retained during updates but does not control the latest screen’s three-second guidance. |

Device imports copy original file contents, and Google Photos imports store the original download file provided by Google. Embedded metadata, such as capture time or location, may therefore remain in the imported copy. The app does not separately extract this metadata to track or analyze your location. The device gallery uses capture-date information from the device media store to sort photos.

## 2. Photo permissions

The photo source screen offers the device gallery and Google Photos. The device gallery reads albums and photos from the device media store and copies only the photos you select into internal app storage. It requests storage read access on Android 12L or earlier and photo read access on Android 13 or later. On Android 14 or later, granting access to selected photos only limits the displayed list to those photos. You can change denied permissions in device settings.

Flows that use the Android system photo picker access only the items you select and do not require broad photo access. Earlier picker-only screens and earlier options labelled Google Photos that opened the system picker use this method. They differ from the new direct Google Photos connection. The new photo source screen and direct Google Photos import are under development; publishing this policy does not establish an app release or completed Google authorization verification.

Direct Google Photos import uses Google's account authorization and selection screens. The app requests only the `photospicker.mediaitems.readonly` scope to read media you select. It does not request access to your entire Google Photos library or albums, email or profile scopes, or a refresh token for offline access. You do not enter your Google account password into the app or provide it to the developer.

You can change or revoke photo permissions in device settings and remove Google access through [your Google account connections](https://myaccount.google.com/connections). Revoking permission or deleting originals may prevent playback of existing original references, but does not automatically delete copies already imported into the app. Later additions to or deletions from original albums are not automatically reflected after a manual import.

When updating from an earlier version, existing photos and playback state are migrated into an app album. Photos previously stored as original device-album URIs may retain those references to avoid data loss. These photos are not automatically synchronized, and deleting originals or changing permissions may make them unavailable for playback. Newly imported photos use internal copies.

## 3. Transfers and third-party services

The app does not send photos or playback settings to a developer-operated server. It does not use advertising, user behavior analytics, or a separate crash-reporting SDK. It declares internet access permission for direct Google Photos import; imported photos can be played offline.

If you choose Google Photos, the app obtains an access token through Google Play services authorization and uses HTTPS to create a Google Photos Picker session, check whether selection is complete, and retrieve selected items. API requests go to `photospicker.googleapis.com`, and photo downloads go to Google's `googleusercontent.com` subdomains. The token authenticates these requests, and photos are downloaded from Google to your device. Google's services and your browser participate in authorization and photo selection; their processing is subject to the [Google Privacy Policy](https://policies.google.com/privacy).

The app holds access tokens, selection session information, and temporary download URLs in memory during the operation, without saving them to files or databases. Account and authorization state managed by Google Play services and your browser follows those services' behavior and settings. Google Photos media identifiers used to detect duplicate imports are stored with the photo list in the app's internal database. The app does not obtain or store a separate refresh token.

Information received from Google Photos is used for the photo imports, app album management, and frame playback you request. Photos and related information are not sold or used for advertising, analytics, or AI training. Use of information received from Google APIs follows the [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy), including its Limited Use requirements, and the [Google Photos API User Data and Developer Policy](https://developers.google.com/photos/support/api-policy).

Google Photos album auto-sync and Ambient API integration are not currently provided. Items marked as coming soon describe future designs; they do not request access or retrieve data for those features.

Cloud photo selection through the system photo picker depends on the photo provider connected to your device and is subject to that provider's privacy policy.

Information processed by Google's own services, such as Google Play distribution, purchases, and device diagnostics, is governed by the [Google Privacy Policy](https://policies.google.com/privacy). Those services are separate from processing performed directly by this app.

This privacy policy website is hosted on GitHub Pages and uses no advertising or analytics scripts of its own. Hosting information, such as visitors' IP addresses, may be processed under the [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement). Photos stored in the app are not transmitted to this website.

## 4. Retention and deletion

Imported photos, source identifiers for duplicate detection, and settings remain on your device to provide the app's features. They do not expire automatically after a fixed period.

When a Google Photos import completes, is cancelled, or encounters an error, the app attempts to delete the Google selection session. Network failures or app process termination can prevent that request from completing; remaining sessions follow Google's expiry policy. Deleting a selection session or removing Google access does not delete previously imported internal photo copies.

The existing single-list version attempts to remove unused internal copies after successfully replacing the photo list or source.

In versions with app albums, imports add photos to the selected app album without replacing its existing contents. You can cancel an import while photos are being copied. Cancellation accepted during this phase, or an import failure, leaves the existing album contents intact. Cancellation is unavailable once copying ends and the app begins finalizing the album save. After an import completes, you can remove its photos as described below. You can remove selected photos or delete an app album within the app. After saving those changes, the app attempts to remove internal photo copies no longer referenced by any app album. Photos used by other app albums are retained. Unused copies may remain after a save failure, unexpected shutdown, or unsuccessful file deletion.

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
