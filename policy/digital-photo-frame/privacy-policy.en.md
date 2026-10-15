# Digital Photo Frame Privacy Policy

- App: Digital Photo Frame / 디지털액자
- Developer: PSH4607 (박성호)
- Contact: [dev.psh30095@gmail.com](mailto:dev.psh30095@gmail.com)
- Revision and effective date: October 15, 2026

This policy explains how PSH4607 handles photos, videos, and settings in Digital Photo Frame. It covers the Android app's photo and video playback features and inquiries sent directly to the developer.

You can identify photo handling by the app’s album management screen. The legacy app, which has no screen for creating or managing named app albums and lets you select only one photo list, reads original device-album URIs and refreshes the list when you return to the app or start the frame. Manual albums in an app with a screen for creating and managing named app albums copy newly imported photos into internal storage cumulatively, without automatic synchronization. Descriptions of app album creation, photo removal, and album deletion below apply to apps with that album management screen. Development builds may display the same version number, so the version number alone does not distinguish these behaviors. Publishing this policy does not itself mean that an app update has been released.

## Device gallery album linking (feature under development)

The following applies only to builds with the “Link a gallery album” feature. It differs from manual imports in existing installations; publishing this policy does not establish a feature release.

Link targets are folder-based albums on the same device where the app is installed and, on Android 11 or later, photos marked as favorites in the system media store (MediaStore). Favorites collect photos on that device using favorite information shared with the system; an empty favorites collection can remain linked and reflect later changes. Favorites kept privately by a gallery app or managed only in the cloud without being shared with the system, people categories, and albums on other devices are not targets. The app stores the linked album’s storage volume and album (bucket or favorites collection) identifiers, name and path, original photo content URIs, and link and playback state in private internal app storage. Linked photos are read from originals without creating internal photo copies.

Linking requires full photo read access. Selected-photo access or denial prevents completing a link. When another system request is available, the app requests access again in response to your action; otherwise it directs you to device settings. If access is revoked or reduced to selected photos after linking, the app preserves the link and existing list and pauses linked-photo playback. It queries again after full access is restored.

The app refreshes the linked folder or system favorites collection when you open the app or start playback, and when device photo changes are detected during playback. This one-way link reflects photo additions and deletions and system favorite selections and removals in the frame list without modifying or deleting gallery originals. Insufficient permission or a query error alone does not delete the link or existing list. Deleting a linked album removes only its app link information, photo list, and playback state.

Long-pressing a linked album and choosing “Unlink album” copies the photos currently in that album to private internal app storage, then converts the same album to a manual album. After conversion, additions and deletions in the original album are no longer reflected automatically; gallery originals are not modified or deleted. The link remains until every photo has been copied and album storage is committed. If copying or saving fails, or you cancel during copying, the existing link and photo list are preserved and temporary copies created by the operation are cleaned up. Successfully converted internal copies follow the retention and deletion behavior below.

Internal copies imported into manual albums retain the existing retention and deletion behavior. Direct Google Photos Picker imports are also unchanged. Google Photos Ambient API integration awaits partner approval and is not provided; screens marked awaiting approval or coming soon do not request access or retrieve data for that feature.

## Photo and video manual albums (feature under development)

In manual albums with photo and video tabs, the photo and video import menus separately offer the device gallery and external sources. The app’s own gallery selection screen provides recent items and album browsing for each media type: photo selection shows only photos, and video selection shows only videos. Only selected items are copied to private internal app storage. Direct Google Photos imports retrieve only the media type chosen in the app from your Google selection; videos must have completed processing at Google. Google’s selection screen may display both photos and videos, but the app filters out the other media type before downloading. Media type and video duration are determined on your device and stored with the album list; video thumbnails are generated on your device. Device-gallery video browsing requires the video access described below. Automatically linked device albums remain photo-only.

Each video plays to the end before advancing, with audio following your device's media volume. Sequential playback shows photos followed by videos; shuffle mixes photos and videos together. The descriptions below of internal-copy retention, deletion, data protection, and no transfers to a developer-operated server also apply to videos. Publishing this policy does not establish a feature release.

## Digital clock and face location detection (feature under development)

The following applies only when you enable the digital clock in a build that includes it. It is offered for manual albums that store photos in the app, not linked albums. Publishing this policy does not establish a feature release.

To place the clock within each photo while avoiding faces and nearby areas, the app detects face locations on your device. It does not identify people, match people across photos, or create face identification embeddings or people profiles. Face locations are used in memory only while calculating automatic placement and are not separately saved. Image dimensions, photo-relative automatic and manually edited clock positions and sizes, per-album clock enablement, and preparation progress and error state are kept in private internal app storage to restore placements. The face detection model bundled with the app runs on your device. This processing does not send photos or detection results to external servers or request new photo access permissions.

The face detector uses Google MediaPipe Tasks Android 0.10.35. When the detector is used, the SDK collects and sends task usage and performance statistics to Google through its logging and transport components. These statistics include app package and version, task type and mode, task session events, processing counts, latency, and initialization errors. The transport also attaches device, operating-system, locale, and network-type information. Google uses these metrics to measure usage and performance and debug, maintain, and improve MediaPipe Tasks, as explained in the [MediaPipe Tasks Privacy Notice](https://developers.google.com/edge/mediapipe/solutions/tasks#mediapipe_tasks_privacy_notice); photos, videos, and detected face locations are not sent in these statistics. Google processes these statistics under its [Privacy Policy](https://policies.google.com/privacy). The app does not provide a separate control to disable SDK statistics while using face detection. Clearing app data or uninstalling removes local app data; it does not constitute deletion of statistics already sent to Google. The developer does not specify a separate retention period for Google's SDK statistics.

Turning off the clock or cancelling preparation may retain completed local analysis and placements for later reuse. Removing a photo or album from the app also cleans up the clock records associated with that item. The retention and deletion section below explains how to remove all app data and how original photos are preserved.

## OneDrive and Dropbox photo and video import and folder linking (under development)

This description applies only to builds that include OneDrive and Dropbox features. Publishing this policy does not establish a feature release or completion of a provider's production review. OneDrive supports personal Microsoft accounts. Choosing a provider opens that service's sign-in and consent screen; you do not provide your password to the app or developer. The app uses Microsoft's MSAL and Dropbox PKCE authorization to request access to read photos, videos, and folders and maintain sign-in. It does not request permission to upload, modify, or delete originals.

Manual albums created in the app download only photos or videos you explicitly select into internal storage. Photo selection and video selection display only the chosen media type. Later additions, changes, or deletions in the cloud are not automatically reflected. A linked folder includes photos directly inside the single folder you select, excluding subfolders and videos. The app checks the list and photo changes approximately every 60 seconds while it is active in the foreground, or when you request a refresh. Continuous background synchronization is not guaranteed.

Linked photos are downloaded to private internal app storage for offline playback. The app stores the provider and account identifiers, display name, linked folder identifier, name and path, photo identifiers and revisions, internal file URIs, and link and playback state on your device. A new list is saved only after the complete listing and required downloads succeed. When a successful synchronization confirms that an original was deleted, its linked membership is removed and internal copies unused by other albums are cleaned up. Expired sign-in, insufficient permission, network errors, and failed downloads alone do not erase existing lists or copies.

Unlinking an album converts it to a manual album while preserving its current internal copies. Disconnecting a provider account removes that provider's sign-in information held by the app, but does not delete existing albums or copies. Updating remaining linked albums requires signing in again. Cloud originals are never modified or deleted by these operations.

Tokens needed to maintain Microsoft or Dropbox sign-in are kept in protected on-device storage according to the authorization method used. Clearing app data or uninstalling removes the app's tokens and internal data. Sign-in state managed by a browser or provider app follows that service's settings; disconnecting in this app does not revoke the service-side consent. You can also revoke access through your Microsoft or Dropbox account's connected-app controls.

Authorization, folder queries, and photo and video downloads use HTTPS directly between your device and Microsoft or Dropbox, without a developer-operated server. Authorization and data requests go to Microsoft sign-in, Microsoft Graph API and download hosts, or Dropbox sign-in, API and content hosts. Their processing is covered respectively by the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement) and [Dropbox Privacy Policy](https://www.dropbox.com/privacy). Downloaded photos and videos may retain metadata embedded in the original file, such as capture time or location. Photos, videos, and related information are not sold or used for advertising, analytics, or AI training.

## 1. Information processed on your device

No app account or registration is required. Playing device photos does not require sign-in; choosing Google Photos, OneDrive, or Dropbox import or folder linking requires authorization and consent for that provider account. The app processes the following information on your device.

| Information | Purpose and storage |
| --- | --- |
| Photos or videos selected from the device gallery, Android system picker, or Google Photos selection screen | Copied to private internal app storage for offline frame playback. Google Photos imports download your selected photos and videos whose processing is complete. |
| Device photos, videos, and album information you permit the app to access | Used to display permitted gallery items, albums, and item counts separately for photo and video selection. On Android 11 or later, the system’s favorite information is read to construct the linked list. The legacy single-list version references originals and refreshes its list. |
| Photo and video paths or URIs, media type and video duration, source URIs or Google Photos media identifiers for duplicate detection, app album identifiers and names, and the default and last played album | Stored in private internal app storage to restore each album and prevent the same source from being added twice to the same app album. |
| Display interval, sequential or shuffle mode, photo size/display mode (Fit, Fill, or Stretch), per-album playback order and position, and legacy usage-hint state | Stored in private internal app storage to restore shared settings and per-album playback state. The legacy hint value is retained during updates but does not control the latest screen’s three-second guidance. |
| App display language selection (follow device language, Korean, English, or Japanese) | Used to retain the display language in builds with language settings. On Android 12L or earlier, AndroidX AppCompat stores the preference in private internal app storage; on Android 13 or later, Android manages it through per-app language settings. It is not sent to a developer-operated server. |

Language settings are under development and apply only to builds that include them. The default follows the device language. You can select Korean, English, or Japanese in the app, or return to following the device language. Language settings do not request new access permissions or send information to a developer-operated server. Publishing this policy does not establish a feature release.

Device photo and video imports copy original file contents, so embedded metadata such as capture time or location may remain in the imported copy. Google Photos photos use the image download option (`=d`), which Google describes as retaining Exif metadata except location metadata. Google Photos videos are stored as the high-quality transcoded version Google provides (`=dv`); preservation of the original file or original metadata is not guaranteed. The app does not separately extract this metadata to track or analyze your location. The device gallery uses capture-date information from the device media store to sort photos and videos.

## 2. Photo and video permissions

The photo and video source screens offer the device gallery and external imports separately. The device gallery reads albums and the chosen media type from the device media store and copies only items you select into internal app storage. It requests storage read access on Android 12L or earlier, photo read access for photo browsing on Android 13 or later, and video read access for video browsing on Android 13 or later. On Android 14 or later, selected-photo-and-video access limits each list to permitted items of its media type. You can change or revoke these permissions in device settings.

Flows that use the Android system photo picker access only the items you select and do not require broad photo access. Earlier picker-only screens and earlier options labelled Google Photos that opened the system picker use this method. They differ from the new direct Google Photos connection. The new photo source screen and direct Google Photos import are under development; publishing this policy does not establish an app release or completed Google authorization verification.

Direct Google Photos import uses Google's account authorization and selection screens. The app requests only the `photospicker.mediaitems.readonly` scope to read media you select. It does not request access to your entire Google Photos library or albums, email or profile scopes, or a refresh token for offline access. You do not enter your Google account password into the app or provide it to the developer.

You can change or revoke photo permissions in device settings and remove Google access through [your Google account connections](https://myaccount.google.com/connections). Revoking permission or deleting originals may prevent playback of existing original references, but does not automatically delete copies already imported into the app. Later additions to or deletions from original albums are not automatically reflected after a manual import.

When updating from an earlier version, existing photos and playback state are migrated into an app album. Photos previously stored as original device-album URIs may retain those references to avoid data loss. These photos are not automatically synchronized, and deleting originals or changing permissions may make them unavailable for playback. Newly imported photos use internal copies.

## 3. Transfers and third-party services

The app does not send photos, videos, or playback settings to a developer-operated server. It does not use advertising or a separate crash-reporting SDK. The MediaPipe task usage and performance statistics described in the digital clock section are an exception to local-only processing. It declares internet access permission for direct Google Photos, OneDrive, and Dropbox integration, that SDK communication, and update and remote-policy checks. Imported photos and videos can be played offline, subject to the mandatory-update restrictions described below.

If you choose Google Photos, the app obtains an access token through Google Play services authorization and uses HTTPS to create a Google Photos Picker session, check whether selection is complete, and retrieve selected items. API requests go to `photospicker.googleapis.com`, and photo and video downloads go to Google's `googleusercontent.com` subdomains. The token authenticates these requests, and photos and videos are downloaded from Google to your device. Google's services and your browser participate in authorization and photo selection; their processing is subject to the [Google Privacy Policy](https://policies.google.com/privacy).

For Google Photos import, the app holds access tokens, selection session information, and temporary download URLs in memory during the operation, without saving them to files or databases. Account and authorization state managed by Google Play services and your browser follows those services' behavior and settings. Google Photos media identifiers used to detect duplicate imports are stored with the photo list in the app's internal database. The app does not obtain or store a separate refresh token.

Information received from Google Photos is used for the photo and video imports, app album management, and frame playback you request. Photos, videos, and related information are not sold or used for advertising, analytics, or AI training. Use of information received from Google APIs follows the [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy), including its Limited Use requirements, and the [Google Photos API User Data and Developer Policy](https://developers.google.com/photos/support/api-policy).

Google Photos album auto-sync and Ambient API integration are not currently provided. Items marked as coming soon describe future designs; they do not request access or retrieve data for those features.

Cloud photo selection through the system photo picker depends on the photo provider connected to your device and is subject to that provider's privacy policy.

Information processed by Google's own services, such as Google Play distribution, purchases, and device diagnostics, is governed by the [Google Privacy Policy](https://policies.google.com/privacy). Those services are separate from processing performed directly by this app.

This privacy policy is hosted on GitHub Pages and Cloudflare Pages and uses no advertising or analytics scripts of its own. Hosting information, such as visitors' IP addresses, may be processed under the respective host's [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement) or [Cloudflare Privacy Policy](https://www.cloudflare.com/privacypolicy/). Photos and videos stored in the app are not transmitted to this website.

## App updates and remote policy (under development)

This description applies only to builds with in-app updates; publishing this policy does not establish an app update release. The app uses Google Play In-App Updates (`app-update:2.1.0`). Google Play processes device metadata, the app version, and installed module and asset-pack lists to determine update availability and expected download size. [Google's guidance](https://developer.android.com/guide/playcore/in-app-updates#data-safety) states that this information is encrypted, is not shared with third parties, and is deleted after a fixed retention period; it does not specify that period. The app does not send photos, videos, or album contents for this update check. Google's processing is governed by the [Google Privacy Policy](https://policies.google.com/privacy) and [Google Play Terms of Service](https://play.google.com/about/play-terms/).

The app downloads the public policy file at `https://psh4607.github.io/policy/digital-photo-frame/update-policy.json` using HTTPS GET to determine the update mode and minimum supported version. It adds no URL parameters and includes no photos, videos, album information, account information, or app-generated user or device identifiers in the request. Comparisons with the installed version take place on your device. GitHub Pages may receive ordinary connection information, such as the IP address and request time, under the [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement). The developer does not use these requests for user behavior analytics or location tracking.

The accepted policy and its revision, the confirmed mandatory-update target version, and the version and time of deferred optional-update prompts are kept in private internal app preferences. They preserve update decisions and deferrals across app restarts and are removed when app data is cleared or the app is uninstalled. Removing this local information does not constitute deletion of information already processed by Google or the hosting provider.

Optional updates are offered only in Settings, and download and restart can be deferred. A mandatory update may interrupt playback and restrict app use after Google Play confirms a compatible update available to the device. Cancelling a mandatory update may leave only retry and exit available. Imported photos and videos remain on the device, but app use, including playback, may be restricted until a confirmed mandatory update is installed. Applying an update requires an app restart.

## 4. Retention and deletion

Imported photos, source identifiers for duplicate detection, and settings remain on your device to provide the app's features. They do not expire automatically after a fixed period.

When a Google Photos import completes, is cancelled, or encounters an error, the app attempts to delete the Google selection session. Network failures or app process termination can prevent that request from completing; remaining sessions follow Google's expiry policy. Deleting a selection session or removing Google access does not delete previously imported internal photo copies.

The existing single-list version attempts to remove unused internal copies after successfully replacing the photo list or source.

In versions with app albums, imports add photos to the selected app album without replacing its existing contents. You can cancel an import while photos are being copied. Cancellation accepted during this phase, or an import failure, leaves the existing album contents intact. Cancellation is unavailable once copying ends and the app begins finalizing the album save. After an import completes, you can remove its photos as described below. You can remove selected photos or delete an app album within the app. After saving those changes, the app attempts to remove internal photo copies no longer referenced by any app album. Photos used by other app albums are retained. Unused copies may remain after a save failure, unexpected shutdown, or unsuccessful file deletion.

To remove all imported photos and settings, use **Storage → Clear storage / Clear data** for this app in Android settings, or uninstall the app. Menu names vary by device. **Clearing the cache alone does not remove all imported photos and settings.** The current app does not have an in-app delete-all button.

Clearing app data or uninstalling the app does not delete originals in your device gallery or cloud photo service. For manual albums, deleting an original from your gallery or cloud service does not remove an imported copy; delete that copy separately using the methods above. OneDrive and Dropbox linked albums follow the successful folder synchronization deletion behavior described above.

The developer cannot remotely access or delete photos and settings stored on your device. There is no app account to close.

## 5. Data protection

Photo copies and settings are stored in internal app storage protected by Android's app access controls. The app provides no cloud backup to its own server or synchronization of app albums between devices and is configured to disable Android automatic backup. Device migration features provided by your device manufacturer are subject to the device's settings and policies.

## 6. Contact and your choices

You can send privacy inquiries to [dev.psh30095@gmail.com](mailto:dev.psh30095@gmail.com). If you contact us, your sender email address, message, and any attachments you choose to provide are delivered by email. We use Gmail to respond to inquiries, so the email service also processes that correspondence. You do not need to send sensitive photos, identity documents, or other material unnecessary for your inquiry.

Correspondence is used to respond to your inquiry and handle your request. It is separate from photos and settings processed locally by the app. Support emails and attachments are deleted within 90 days after the inquiry is closed.

You can change permissions and delete app data through device settings. You can also contact the privacy email address to request access to, correction of, or deletion of information you provided directly in correspondence.

## 7. Changes to this policy

If the app's data handling changes, we will update this policy and any necessary in-app notices, identifying the revision and effective dates.
