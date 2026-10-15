# Digital Photo Frame public pages

- App homepage (English and Korean): https://psh4607.github.io/policy/digital-photo-frame/home.html
- English: https://psh4607.github.io/policy/digital-photo-frame/
- Korean: https://psh4607.github.io/policy/digital-photo-frame/ko.html
- Policy revision and effective date: October 15, 2026. Support emails and attachments are deleted within 90 days after the inquiry is closed.
- The policy distinguishes the single-list app from the named-album app by the presence of an album management screen, not by a broad version-number range. Cancellation is available while copying photos and disabled while the album save is finalized. Publishing a policy revision does not establish that an app update has shipped.

The Markdown files are the editable source; index.html and ko.html are static rendered copies. Regenerate both HTML files when updating the corresponding Markdown. No client-side JavaScript, analytics, or external fonts are used. These files are independent of the existing policy/gcp pages.

## 2026-10-09 사진 선택기 전용 화면 안내 보완

최신 개발 화면은 ‘사진 추가’에서 시스템 선택기를 바로 열며 새 사진 추가를 위해 전체 사진 읽기 권한을 요청하지 않습니다. 이전 기기 앨범 기능과 기존 원본 URI 재생을 위한 권한 선언을 구분했습니다. 사진 복사·삭제·문의 보관 기준은 유지합니다. 앱 변경의 배포와 정책 웹페이지 배포는 별개입니다.

## 2026-10-10 retained playback preference disclosure

Both policies now disclose the persisted Fit/Fill/Stretch photo display preference and distinguish the retained legacy hint value from the current three-second guidance. Photo handling and the 90-day support retention rule are unchanged.

## 2026-10-11 device gallery and direct Google Photos import

The policies describe device photo permissions and optional Google Photos Picker authorization, selected photo downloads into private offline storage, local media identifiers for duplicate detection, memory-only operation tokens/session data, best-effort session deletion, and removal of Google access separately from deletion of imported photos. Google data use is limited to requested imports, app album management, and frame playback. Auto-sync and Ambient integration are not offered. The 90-day support retention rule is unchanged. Policy publication does not establish an app release, Google authorization verification, or partner approval.

## 2026-10-12 terms of service

- English: https://psh4607.github.io/policy/digital-photo-frame/terms.html
- Korean: https://psh4607.github.io/policy/digital-photo-frame/terms-ko.html
- Terms revision and effective date: October 12, 2026.
- Editable sources: `terms-of-service.en.md` and `terms-of-service.ko.md`; static rendered copies: `terms.html` and `terms-ko.html`. Keep both languages aligned when revising them.
- The homepage links to both terms pages; each terms page links to the homepage, the other language, and the matching privacy policy. Privacy-policy content and the 90-day support retention rule are unchanged.
- Publication does not establish Google OAuth verification approval, an app release, or implementation of an in-app terms consent flow.

## 2026-10-13 same-device gallery album linking

Both languages describe the linked folder feature as build-dependent and under development: original URI references without copies, locally retained album identifiers and state, full photo read permission, permission restoration and paused playback, one-way additions/deletions, and unlinking without modifying originals. Manual imports and the 90-day support retention rule are unchanged. Google Photos Ambient partner approval is pending; policy publication does not establish a feature release.

## 2026-10-13 unlinking into a manual album

Unlinking a device album copies every photo in the current app album into private internal storage before converting that same album to a manual album. Subsequent changes in the source album are no longer reflected. Failure or cancellation preserves the original link and list and cleans temporary copies; deleting a linked album remains a separate action. Gallery originals and the 90-day support retention rule are unchanged. Policy publication does not establish an app release.

## 2026-10-13 system favorites linking

On Android 11 or later, the app can link the device's system MediaStore favorites collection, including when it is empty, and reflect later favorite selections and removals. Gallery-private or cloud-only favorites not shared with MediaStore, people categories, and albums on other devices are excluded. Android 10 or earlier remains folder-only. No additional permission, network transfer, or original-photo modification is introduced. The existing unlink-to-manual behavior and 90-day support retention rule are unchanged. Publishing this policy does not establish an app release.

## 2026-10-14 app language preference

Both languages disclose the build-dependent language setting (follow device language, Korean, English, or Japanese), on-device storage through AndroidX AppCompat on Android 12L or earlier, and Android per-app language settings on Android 13 or later. No new access permission or developer-server transfer is introduced. The 90-day support retention rule is unchanged. Policy publication does not establish an app release.

## 2026-10-15 manual photo and video albums

Builds with media tabs import user-selected videos through the Android system picker or ready Google Photos videos into private local storage. Policies disclose media type and duration, local thumbnails, full-length playback with device audio, sequential photos-then-videos and mixed shuffle. Existing gallery selection and linked albums stay photo-only, no broad video permission is added, and existing retention/deletion and 90-day support commitments remain. Hosting disclosure now names both GitHub Pages and the Cloudflare Pages mirror at https://photo-frame.seongho.dev/ (Korean: /ko). Policy publication does not establish an app release or Google authorization approval.

## 2026-10-15 Google download-format clarification

The policies distinguish device originals, Google image downloads (`=d`, Exif except location), and high-quality transcoded Google video downloads (`=dv`). Original video files or metadata are not guaranteed. This follows Google's Picker media-items guide: https://developers.google.com/photos/picker/guides/media-items . No app data handling or retention commitment changed.
