# Implementation and disclosure basis

Reviewed on October 8, 2026 for Multi Space (`com.multispace.appcloner`). The Android project was read only; this website change does not modify its package, certificate, engine, account storage, Firebase configuration, or UI.

## Repository state

The supplied GitHub repository was empty: no prior page, README, AGENTS.md, legal text, or default branch existed. A small static brand landing page was added instead of assuming an existing website framework.

## Android source basis

Paths below are relative to the separate PhantomMultiSpace Android project.

| Disclosure | Reviewed source | Basis and boundary |
| --- | --- | --- |
| Installed application names, versions, package information and icons | `app/src/main/java/com/multiapp/morespace/app/ui/apps/AddAppViewModel.java`; `app/src/main/AndroidManifest.xml` | Source application selection and broad package visibility; declaring a permission alone is not proof that every data item is read. |
| Local organization metadata and retired IDs | `app/src/main/java/com/multiapp/morespace/app/ui/home/instance/InstanceMetadataStore.java`; `InstanceRepository.java` in the same directory | Package/user locator plus per-lifetime UUID; custom labels/icons/workspaces, inactive records retained; a workspace deletion moves instances to the default group. |
| Diagnostics preview and user-directed export | `app/src/main/java/com/multiapp/morespace/app/ui/system/DiagnosticsFragment.kt` | Report is previewed locally and exported through Android's user-selected document destination, not automatically sent to support. |
| Engine and application data | `app/src/main/java/com/multiapp/morespace/app/App.java`; `engine-compat/src/main/java/com/wish/sdk/api/WishApi.java` | Local container attachment and instance device configuration. The native engine is a binary dependency; this source review does not establish that every internal engine operation has been audited. No promise that all guest content stays offline is made. |
| Sensitive permissions and guest functionality | `app/src/main/AndroidManifest.xml` | Declares contacts, calendar, microphone, camera, location, phone/account and media capabilities, among others. Actual access depends on Android grants, engine support, and application behavior. |
| Firebase configuration | `app/src/main/java/com/multiapp/morespace/app/ui/update/AppUpdateConfigSource.kt`; `AppUpdatePolicy.kt` in the same directory; `app/src/main/java/com/multiapp/morespace/app/ui/apps/GoogleComponentsVisibilityConfig.kt` | Manual Firebase initialization and configuration fetch/activation for update gates and component-entry visibility. Configuration is cached locally. The interface does not provide installed-app lists, account contents, or custom labels as Remote Config parameters. |
| Disabled commercial telemetry and purchases | `app/src/main/AndroidManifest.xml`; `app/build.gradle.kts`; `app/src/main/java/com/multiapp/morespace/app/gp/App.java`; `MainActivity.kt` in the same directory | Analytics and Crashlytics collection default to false; eager ad/Firebase providers removed; current INTERNAL_BUILD path avoids commercial ad and purchase startup. Remote Config remains active and must be disclosed independently. |
| Android backups | `app/src/main/res/xml/backup_rules.xml`; `data_extraction_rules.xml` in the same directory | Virtual directory `ebzl`, `virtual_items`, and legacy rename preferences are excluded. Other metadata/preferences are not comprehensively excluded; the policy does not claim no system backup. |
| Published identity and private contact | Confirmed directly by the owner for this website | Developer name `mulitispaces`; public contact `ymwotow411846@gmail.com`. This is the owner's provided publisher identity, not an invented company or jurisdiction. Email is the privacy request channel; GitHub Issues is only an additional public channel for non-sensitive questions. |

## Official references checked

- [Google Play User Data policy](https://support.google.com/googleplay/android-developer/answer/10144311?hl=en): public HTML policy, app/developer identification, privacy inquiry mechanism, data handling, security, retention/deletion, and consistency with Data safety.
- [Firebase Android data-disclosure information](https://firebase.google.com/docs/android/play-data-disclosure): Remote Config and Firebase Installations technical data. The latest SDK disclosure is a reference, not a substitute for inspecting the shipped version and configuration.
- [Privacy and Security in Firebase](https://firebase.google.com/support/privacy): configuration service identifiers, service logs, processing locations, HTTPS and provider retention.
- [GitHub General Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement): website hosting and public support-provider handling.

The pages summarize relevant behavior in original wording. They preserve non-waivable consumer/privacy rights and do not invent a governing jurisdiction, arbitration requirement, broad waiver, company entity, or fixed deletion deadline.

## Verification boundaries

Local browser checks cover readable full HTML, working internal navigation and section anchors, the existing brand logo, responsive layouts and system light/dark styling. They do not establish deployment to GitHub Pages, approval by Google Play, independent auditing of the binary engine or every guest application, or compliance with every jurisdiction's law.

Before submitting the public URL, verify the contact details against the store listing, actual deployed HTTPS response, app access to the policy, actual shipped SDK behavior, and an accurate Play Console Data safety declaration. If a jurisdiction requires additional operator or representative details, add the real details supplied by the operator. Current Android settings include earlier policy URLs under another domain and a newer policy-not-published help note; wiring the newly deployed URLs into the app is a separate Android change.
