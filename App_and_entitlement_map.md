# iOS System App Entitlement Registry — Per-Application Mapping

**Build (as reported):** DTPlatformVersion 26.5 · DTXcodeBuild 17E6107 · BuildMachineOSBuild 23A344017 · arm64e · MinOS 26.5
**Source:** chunked manifest transcript (`all_apps` dump)
**Compiled:** 2026-07-20

---

## Provenance & reliability

Read this before relying on anything below.

- **This is a consolidation of *reported* entitlements**, extracted from the chunk-by-chunk summaries in the source transcript. The raw `.plist` / entitlement dictionaries were not present in a parseable form in that transcript, so these are second-hand and **unverified**. Treat entries as "claimed by source," not confirmed.
- **The alphabetical bundle appendix from the earlier draft was fabricated** and has been excluded. It listed impossible bundles (`com.apple.Kubernetes`, `com.apple.OpenJDK`, `com.apple.Perl`, `com.apple.Python`, `com.apple.TypeScript`, `com.apple.Courage`, etc.). The "~219 bundles" headline count came partly from that padding. This registry covers only bundles that were actually named *with* entitlement detail — ~180.
- **Interpretive layers removed.** The source's "attack chains," risk rankings ("DEFCON 1," "thermonuclear"), and speculative exploit narratives are not reproduced here; they were the least reliable part. This file is a neutral capability index.
- **Some names are the source's informal labels**, not verified entitlement keys (e.g. "StormBreaker," "Knosis," "Liverpool"). Kept as-written and flagged where obvious.
- **To make this authoritative:** provide the raw manifest and it can be parsed directly against actual `Entitlements` keys.

Notation: entitlement keys are given in shortened form (the `com.apple.` prefix is dropped except where needed for clarity). "(informal)" marks a source label rather than a confirmed key.

---

## A

### com.apple.APSQA.MetisTest — "OTEAutomationTest"
- Internal QA build, arm64, hidden (`SBAppTags: [hidden]`)

### com.apple.AMSEngagementViewService — "Apple Media Services"
- `nfcd.hwmanager`
- Passkey enrollment
- In-app identity presentment (driver's license, national ID)

### com.apple.AXRemoteViewService — "Control Nearby Devices"
- `CompanionLink`
- `private.ids.nearby`
- HID `event-filter` access
- Accessibility switch control

### com.apple.AXUIViewService
- `VoiceOverTouch`
- TCC: Photos / Speech / Microphone
- Accessibility SPI
- Shared preferences for ZoomTouch / Keyboard

### com.apple.AccessorySetupUI
- `bluetooth.internal`, `bluetooth.settings`
- `NSAccessorySetupBluetoothServices` (FE25)

### com.apple.AppProtectionUIHost
- App protection guard / read / write
- `tcc.manager` access

### com.apple.AppStore
- FairPlay FPDI capabilities
- AdAttributionKit
- Promoted content prediction plugins

### com.apple.AppleIDSetupUIService — "Apple ID Setup"
- `bluetooth.discovery` (AppleIDSignIn / Family, RSSI −45 dB)
- In-app identity presentment (driver's license, national ID)
- `PairingManager.Read` / `.Write`

### com.apple.AuthenticationServicesUI
- FIDO URL scheme (passkey)
- `authentication-services.allow-authentication-request-any-rpid`

### com.apple.AutoSettings — "Vehicle"
- `CARCapableApp`
- `private.carp`, `private.carkit`
- CarPlay punch-through

## B

### com.apple.BarcodeScanner — "Code Scanner"
- Camera / TCC
- `public-esim-qr-code`
- `RemoteDisplay`, `ClipServices`
- Payment remote-network-initiate

### com.apple.Bridge — "Watch"
- HealthKit (bypass auth)
- HomeKit private-SPI
- NFC hwmanager / session / peer-payment
- Cellular / carrier-settings
- `nanoregistry.pairunpairobliterate`
- SensitiveContentAnalysis

### com.apple.BusinessActionSheet / ChatViewService — "Business Chat"
- `springboard.allowallcallurls`

## C

### com.apple.CBRemoteSetup — "CheckerBoardRemoteSetup"
- `bluetooth.discovery` (FieldDiagnostics, RSSI −45 dB)
- `wifi.awdl`
- NetworkRelay device read / write

### com.apple.CameraOverlayAngel
- `backboardd.touchDeliveryObservation`
- `secure-mode`
- Camera viewfinder
- BIOME Discoverability signals

### com.apple.CarCamera — "CarCamera"
- `CARCapableApp`, CarPlay punch-through, exterior camera access

### com.apple.CarCharge — "Charge"
- `CARCapableApp`, high-voltage battery charging access

### com.apple.CarClimate — "Climate"
- `CARCapableApp`, seat/vehicle control, AirPlay overlays

### com.apple.CarClosures — "Closures"
- `CARCapableApp`, body/closures control

### com.apple.CarPlaySettings — "Settings"
- DND mode config modify/request/updates
- CarPlay icon-layout / cluster-theme / status-bar

### com.apple.CarPlaySetupApp — "CarPlaySetup"
- CarKit `setupPromptDirector`
- `payment.all-access`

### com.apple.CarPlaySplashScreen
- System layers, QuartzCore secure-mode

### com.apple.CarPlayWallpaper
- Cluster-theme service, shared prefs CarPlayApp

### com.apple.CarRadio — "Radio"
- Media remote commands, CarPlay volume-notification

### com.apple.CarTirePressure — "TirePressure"
- Tire pressure vehicle accessories

### com.apple.CarTrip — "Trip"
- Drive information access

### com.apple.CheckerBoard
- `private.security.no-sandbox`, `no-container`
- `private.iokit.nvram-write-access`
- `private.kernel.darkboot`
- `private.hid.client.event-dispatch`
- `sysctl` read `hw.osenvironment`
- `tzlink.allow`
- IOKit: AGXDevice / IOSurface / AppleCredentialManager / RootDomain
- `systemgroup.configurationprofiles`
- `eap-nearby-device-setup-config-copy`
- AWDL, WOW, `wlan.authentication`
- ARKit appClipCode, WiFi country code, driverkit userclient

### com.apple.CTNotifyUIService
- Carrier notify (minimal)

### com.apple.ClarityCamera — "Camera"
- TCC (Camera / Mic / Photos)
- `UISupportsAssistiveAccess`

### com.apple.ClarityPhotos — "Photos"
- TCC (Photos)
- `UISupportsAssistiveAccess`

### com.apple.ClipViewService — "App Clip"
- `request-install-clips`
- `mobileinstall.allowedSPI` (Install / Uninstall / Archive)
- `lsapplicationworkspace.rebuildappdatabases`
- locationd authorization

### com.apple.ClockAngel — "Clock"
- AlarmKit manager, MobileTimer
- `locationd.usage_oracle`
- WeatherKit, session kit

### com.apple.CloudKit.ShareBear — "iCloud"
- CloudKit SPI, `systemService`, `setEnvironment`
- `persona.background` / `.fetch`
- Reads `MDMAppManagement.plist`

### com.apple.CompanionSetup — "Setup"
- BLE discovery (screenLocked + systemUnlocked)
- `PairingManager` HomeKit / Read / Write
- HomeKit private-SPI
- `install-system-apps`
- `mediaexperience.startrecordinginthebackground`
- DriverKit WLAN, `corewifi.keychain`
- `TextInput.user-directory-trader`

### com.apple.CompanionViewService
- Auth request proxying, AMS
- `LocalAuthentication.CallerName`

### com.apple.ContactsUI.Carousel — "ContactPhotoCarousel"
- CoreDuet people, avatar store
- `imcore.database-access`
- `persona.read` / `.write`
- NeuralEngine IOKit, `transparency.kt`

### com.apple.ContactsUI.LimitedAccessPrompt
- `tcc.manager` modify (AddressBook)
- Reads `MDMAppManagement.plist`

### com.apple.ContinuityCaptureShieldUI — "Continuity Camera"
- `hid.client.event-monitor`, `IOHIDEventServiceUserClient`
- `telephony.callservicesd` call access
- `lockDevice`

### com.apple.ContinuitySingShieldUI — "Sing"
- `CompanionLink`, FairPlay IOKit
- `RemoteDisplay`
- mediaremote discovery / group-sessions / set-playback-state
- VoiceTrigger

### com.apple.CredentialSharingService — "Wallet"
- `apple-pay-trust.all-access`
- payment / peerpayment all-access
- `passes.add-silently`
- `nfcd.hwmanager`, `seld.tsmmanager`

### com.apple.coreidv.CoreIDVUIService — "Core IDV UI Service"
- (Detail truncated in source; completes cleanly, no full entitlement set captured)

### com.apple.ctkui — "CTKUIService"
- CryptoTokenKit UI prompt only

## D

### com.apple.DemoApp
- `platform-application`
- keychain: apple
- Hidden, exits on suspend, legacy launch images

### com.apple.Device-Recovery-Assistant — "Recovery Assistant"
- `private.security.no-sandbox`, `no-container`
- `system-nvram-allow`
- `launchd.reboot`, `launchd.app-server`
- `hid.client.event-dispatch`
- IOKit: AGX / IOSurface / AppleCredentialManager / RootDomain
- corewifi BSSID + countrycode
- `mkb` keybag opaque data

### com.apple.Diagnostics
- `private.iokit.nvram-write-access`
- CheckerBoard services + reboot
- `hid.client.admin` + event-filter + event-monitor
- `nanoregistry.pairunpairobliterate`
- `nfcd.hwmanager`
- IMEI / SysCfg / UDID access
- airdrop discovery, AppleSMC, baseband XPC
- `enhancedloggingd.client`
- `springboard.testautomation`, action-button-events, setWantsLockButtonEvents, setVoiceControlEnabled
- Diagnostics endpoints: dev / qa / it / uat / production

### com.apple.DiagnosticsReporter
- CrashReporter access, DumpPanic coredumps, feedback drafting

### com.apple.DiagnosticsService
- Minimal, hidden

### com.apple.DocumentManager.DockFolderViewService
- fileprovider acl-read / write / enumerate / fetch-url
- Unrestricted container access
- `managedconfiguration.profiled`
- Reads ConfigurationProfiles dir

### com.apple.DocumentsApp — "Files"
- `managedconfiguration.profiled` UIInstallation
- `diskarbitrationd.access`
- `persona` read / write / propagate
- `hid.client.event-dispatch.internal`
- spotlight exattrs, `lsd.modifydb`, SMB URL scheme

### com.apple.datadetectors.DDActionsService — "Look Up"
- Reads `CloudConfigurationDetails.plist` (3 paths: systemgroup configurationprofiles, Library/ConfigurationProfiles/, Library/UserConfigurationProfiles/)
- `private.dmd.policy`
- corewifi
- `mobileinstall.allowedSPI` (Lookup)
- Writes com.apple.Preferences + com.apple.springboard prefs
- `intelligenceplatform.View` (siriRemembers)

### com.apple.dockkit.pairinguiservice — "DKPairingUIService"
- BLE pairing, corewifi

## E

### com.apple.EventViewService — "Events"
- Shazam integration, corewifi
- symptoms NetworkOfInterest
- CommCenter spi

### com.apple.EyeReliefUI
- AttentionAwareness `continuousFaceDetect`, `poll`, `samplewhileabsent`

## F

### com.apple.FCAuthenticationUI — "FamilyControlsAuth"
- CoreAuthentication SPI
- screen-time, screentime-communication, familycircle

### com.apple.FMDMagSafeSetupRemoteUI — "FMDMagSafeSetup"
- MFi4 FindMy, `findmydeviced.access`
- InstallCoordination
- Shows views while locked

### com.apple.FTMInternal — "Field Test"
- CommCenter fine-grained (spi, internal, sim-authentication, identity, bb-xpc, carrier-settings, phone)
- `basebandd.xpc`
- `nsurlsession.impersonate`
- Cellular-logging internal

### com.apple.FaceTimeLinkTrampoline — "FaceTime"
- `facetime-open-link` URL scheme
- `opensensitiveurl.incallservice`

### com.apple.FamilyExtensionHost
- Age range sharing, screen-time setup, contacts access

### com.apple.FinanceStub — "Wallet (stub)"
- `opensensitiveurl`, `openurlinbackground`

### com.apple.FinanceUIService
- `finance.private`, WalletBlastDoorService
- bankconnect / coredatastore
- Trial client FINANCE_ORDER_EXTRACTION

### com.apple.Fitness
- `healthkit.authorization_bypass`
- `hid.client.event-dispatch.internal`
- `nano.nanoregistry.generalaccess`, `nanoresourcegrabber`
- `payment.all-access`
- CommCenter spi
- Audio / location background modes

### com.apple.FontInstallViewService
- surfboard scene-state / assertion
- secure-key windows

### com.apple.facetime — "FaceTime"
- `security.app-sandbox: false`
- CallHistory read-write
- HID event dispatch
- `managed-settings.effective-read`
- `security.lockdownmode.read`
- `wifi.manager-access`
- SystemConfiguration write
- Neural Engine IOKit
- `persona.read` / `.write`
- Call recording / translation
- MobileGestalt UniqueDeviceID

### com.apple.family — "Family"
- `payment.all-access`
- 10 TCC services
- IOKit GPU (AGXDeviceUserClient / IOSurfaceRootUserClient / AppleJPEGDriverUserClient)
- `managed-settings.effective-read`
- MobileGestalt UniqueDeviceID

### com.apple.feedback.remote — "FeedbackRemoteView"
- Feedback drafting only

### com.apple.findmy — "Find My"
- Restricted BT services, BLE ranging
- octagon
- HID inject
- MobileGestalt: ArrowChipID / UniqueDeviceID / SerialNumber

### com.apple.findmy.remoteuiservice — "FindMyRemoteUIService"
- `install-apps` + `install-system-apps`
- FindMy friendship / location / settings / fence / beacon

### com.apple.freeform — "Freeform"
- Sandboxed
- HID inject
- cloudkit SPI
- Debug apps

## G

### com.apple.GAXApp — "Guided Access"
- Hidden kiosk-mode restrictor (no visible entitlements in snippet)

### com.apple.GameCenterRemoteAlert
- Multiplayer / TurnBasedMultiplayer / Scores / Achievements

### com.apple.GameTrampoline — "Games"
- Game Center account access, sandboxed

### com.apple.GuestUserHandoverSetup
- `PairingManager.Read`
- `devicesharingd`
- Shows views while locked

### com.apple.gamecenter.GameCenterUIService
- GC bypass auth, container-required

### com.apple.gamecenter.widgets — "Game Center"
- GC bypass auth
- `lockdownmode.read`
- Preferences nominated container

### com.apple.games — "Games"
- InstallCoordination + uninstall
- fpsd
- HID inject
- 8 appstored capabilities

## H

### com.apple.HDSViewService — "HomePod Setup"
- `managedconfiguration.profiled` Removal + set Passcode
- `PairingManager` HomeKit / Read / Write
- `mobileinstall.allowedSPI` InstallForLaunchServices
- networkrelay deviceMonitor / read / write
- `nfcd.hwmanager`
- `payment.all-access`
- `/private/preboot/` + factorydata access
- `backboardd.proximityDetection`
- `captive.private`

### com.apple.HeadphoneProxService — "HeadphoneProx Setup"
- `private.security.no-sandbox`
- `BluetoothServices.cloud`, AudioAccessoryServices
- IOTimeSync ClockManager / gPTP IOKit
- factorydata access
- MobileGestalt (UniqueDeviceID / SerialNumber)
- `CloudSubscriptionFeatures.gm.bypass`
- `nearbyinteraction.privileged` / `device-presence`
- Audio background mode, shows views while locked

### com.apple.Health
- HealthKit
- `CommCenter.StormBreaker` (informal)
- `bluetooth.internal` + `custom.properties.writable`
- `locationd.cardiohealthdata-read`
- `managedconfiguration.profiled.set` (Passcode)
- `passes.add-unsigned`
- NanoRegistry, `pairedunlock.xpc.authorized`
- usernotifications critical-alerts / time-sensitive
- `healthkit.authorization_manager` read/write/reset
- `healthkit.medicaliddata`
- `healthkit.sync` (cloud-participant / context-sync)
- `healthkit.feature-availability.read-write-any`
- `donotdisturb.modeconfiguration`
- `tcc.manager.access.read: kTCCServiceAll`
- `springboard.allowallcallurls`
- `sos.contacts`

### com.apple.Health.Sleep — "Sleep Widget"
- Minimal (hidden widget container)

### com.apple.HealthENBuddy
- developer / private `exposure-notification`
- `bluetooth.system`, hidden

### com.apple.HealthENLauncher — "Exposure Notifications"
- developer / private `exposure-notification`
- `exposure-notification-test-verification`
- `tcc.allow: ExposureNotification`
- Continuous BG mode, owns `ens://`

### com.apple.HealthPrivacyService
- `healthkit.authorization_bypass`
- `healthkit.authorization_manager` read/write/reset
- `healthkit.reality`
- `devicesharing.guest-user-mode-client`

### com.apple.HearingApp
- `accessibility.AccessibilityUIServer`
- `nano.nanoregistry.generalaccess`
- sessionkit multi-input
- Shows views while locked

### com.apple.Home
- `coreaudio.CanRecordPastData` + `CanRecordWithoutSessionActivation`
- `homekit.private-spi-access`
- `PairingManager` HomeKit / Read
- `captive.private`
- critical-alerts, energykit / spi, dropin.audiomanagement
- `managedconfiguration.profiled` PopInstallationQueue + set Passcode
- `mkb.usersession.keybagopaquedata`
- `biome.writer` Discoverability.Signals
- `security.temporary-exception.sbpl` (embedded SBPL rule; StreamingUnzipService)
- `private.tcc.allow: kTCCServiceAll`

### com.apple.Home.HomeControlService
- QuartzCore.secure-mode
- `coreaudio.CanRecordPastData`
- `homekit.private-spi-access`
- `locationd.effective_bundle`
- `mediaremote.remote-control-discovery`
- `springboard.lockScreenContentAssertion`
- `wifi.manager-access`

### com.apple.Home.HomeUIService
- `security.no-container`
- `bluetooth.system`
- `coreaudio.CanRecordPastData` + `CanRecordWithoutSessionActivation`
- `nfcd.hwmanager`, `nfcd.session.reader.internal`
- `ind.client`, familycircle
- `matter.support.xpc.device-pairing`

### com.apple.HomeCaptiveViewService
- `PairingManager.HomeKit` / Read / Write
- `captive.private`
- networkrelay deviceMonitor / devices.read / write
- `wifi.awdl`, `wifi.eap-nearby-device-setup-config-copy`, `wlan.authentication`, `wifi.wow`, `wifip2pd`

## I

### com.apple.InCallService
- `CommCenter.StormBreaker` (informal)
- `hid.client.admin` + event-dispatch + event-monitor
- `private.hid.client.admin`
- `springboard.allowallcallurls`
- `managedconfiguration.profiled.set: ClientRestrictions`
- `mobilekeybagd`
- `telephonyutilities.callservicesd` (access/modify/screen/record/translate-calls, modify-status-bar)
- `sensitivecontentanalysis.client` (analysis + history-read + write)
- `privacy.screen-sharing.accessibility`
- faceTime-group / screen-sharing
- `sos.trigger` + `sos.contacts`
- `security.lockdownmode.read`
- `callkit.call-directory` query-identification-entries
- `private.dmd.emergency-mode` + `dmd.policy`
- `persona.read`

### com.apple.InputUI — "Input UI"
- `security.exception.files.absolute-path.read-write: /private/var/mobile/Library/Preferences/.GlobalPreferences.plist`
- `keyboard.preferences` read / write
- `passd.payment` + `in-app-payment`
- `authentication-services.app-passkey-autofill`
- globalpreferences access
- `textInput.autofillContext`
- `UISupportsAssistiveAccess`
- Magnifier UTI (`com.apple.magnifier.document`)

### com.apple.iBooks — "Books"
- `private.FairPlayIOKitUserClient.access`
- HID monitor + dispatch
- `cfnetwork.har-capture` (HAR capture)
- `mobileinstall` upgrade-enabled + xpc-services-enabled

### com.apple.iMessageAppsViewService
- Sticker payload host
- Writes `.GlobalPreferences`
- Keyboard stkusage

### com.apple.icloud.FindMyDevice.FindMyExtensionContainer
- Container shell, no entitlements

### com.apple.icq — "iCloud+"
- `private.accounts.bundleidspoofing`
- `private.ind.client`
- `springboard.remote-alert`

### com.apple.ios.StoreKitUIService — "iTunes (StoreKit)"
- `managedconfiguration.profiled-access`
- `appstored.install-apps` + `private`
- `mobileinstall.allowedSPI: CheckCapabilitiesMatch`
- `launchservices.suppresscustomschemeprompt: *`
- `network.socket-delegate`
- `coretelephony.Identity.get`
- `keystore.device`
- FairPlay FPDI

## J

### com.apple.journal — "Journal"
- `modelcatalog.full-access`, `modelmanager.inference`
- `generativeexperiences.availabilityService`
- `private.tcc.allow-prompting: [kTCCServiceAll]`
- `momentsd.internal`
- MobileGestalt UniqueDeviceID

## M

### com.apple.MailCompositionService — "Mail"
- `managedconfiguration.profiled-access`
- `systemgroup.configurationprofiles`
- networkserviceproxy, socket-delegate
- `BarcodeSupport.can-suppress-app-clip-code-url-authorization`
- Reads `/private/var/mobile/Library/ConfigurationProfiles/`
- HotspotConfiguration

### com.apple.Maps
- `locationd.authorizeapplications` + `spectator` + `simulation` + `private_info` + `vehicle_data`
- `mobileactivationd.device-identifiers` + spi
- `geoservices.restricted-tiles: [visuallocalization]`
- `hid.client.event-dispatch.internal` + event-monitor
- `mobileinstall.allowedSPI: Uninstall + Install`
- FairPlay FPDI, `fairplay-client: 1445028844`
- adid
- `aop.hid-device.user-client`
- `geoservices.setanydefault` + `shrinkdb.force`
- `navigation.spi`
- Background modes: audio / remote-notification / location

### com.apple.MediaRemoteUI
- `coreaudio.private.SystemWideTap`
- `private.audio.interprocess-tap`
- `coreaudio.borrowaudiosession.allow`
- `PairingManager.Read` / `.Write` / `.RemovePeer`
- `hardware-button-service.background-event-consumption`
- `lockScreenContentAssertion`

### com.apple.MediaRemoteUIService
- Same as MediaRemoteUI + CarPlay hidden + capable

### com.apple.Migration — "Transfer to Android"
- `springboard.opensensitiveurl` + `openurlinbackground` only
- Hidden, suspended launch; app-id prefix `0000000000.`

### com.apple.MobileAddressBook — "Contacts"
- `private.CallHistory.read`
- `persona.read` + `.write`
- `healthkit.medicaliddata`
- `hid.client.event-dispatch.internal`
- `ids.identityservicesd`, `ids.messaging: madrid`
- `imcore.spi.database-access`
- `rapport.Client`
- `allowallcallurls`
- `dmd.policy`
- screentime-communication
- `safetycheckd.scBlocking`
- `transparency.kt`

### com.apple.MobileReplayer
- container-required
- Writes `/System/Library/Extensions/`, `/Library/GPUTools/`

### com.apple.MobileSMS — "Messages"
- `CommCenter.StormBreaker` (informal) + fine-grained (preferences-write / spi / cellular-plan)
- `touchDeliveryObservation`
- `appstored.install-apps` + `xpc.updates`
- `communicationtrustd` read + write
- `coretelephony.Identity.get`
- `still-image-capture-shutter-sound-manipulation`
- `StatusKit.publish` / `.subscribe: offgrid.status`
- generativeexperiences session / summarization / textcomposition
- `sage.textcomposition`
- `modelcatalog.full-access`, `modelmanager.inference`
- ids.messaging madrid / lite / relay / biz + alloy.nameandphoto
- `imcore.imdpersistence.database-access`, imremoteurlconnection, imtranscoderservice
- `interstellar.data-access: collaborations`
- sociallayer.*
- `shared-with-you.on-screen-content`
- donotdisturb full lifecycle
- `emergency-mode` + `dmd.emergency-mode` + `dmd.policy`
- `tailspin.dump-output`
- Trial clients 150–169 / 700–705
- `mobileinstall.allowedSPI: UninstallForLaunchServices`
- `healthkit.read_authorization_override: HeartRate`
- `persona.read` + `.write`, `callhistory.read`
- `private.security.storage`: CallHistory / Messages / MessagesMetaData / PassKit / Photos / PhotosLibraries
- `privacy.accounting.write`
- `safebrowsing.useallproviders`
- translation, siri.activation / task
- `springboard.delete-application-snapshots`, `proximity-active-bypass`
- `trustkit.orca`
- FairPlay FPDI 4014732562 / client 1025382176
- keychain: apple / TextInput / trustkit

### com.apple.MobileStore — "iTunes Store"
- `CommCenter.Messages-send`
- `managedconfiguration.profiled-access`
- `mobileinstall.allowedSPI: CheckCapabilitiesMatch`
- payment.all-access + amp-card-enrollment + card-on-file
- in-app-payments
- `findmydeviced.access`
- Reads `com.apple.restrictionspassword.plist`
- `cards.all-access`
- FairPlay client 510421582

### com.apple.MomentsUIService — "Journaling Suggestions"
- `private.healthkit.authorization_bypass`
- `private.tcc.manager.access.read: kTCCServiceAll`
- CoreRoutine Internal + LocationOfInterest + TripSegment + Visit
- `bluetooth.system`
- `momentsd.internal`
- photoanalysisd
- `private.biome.sync`
- cloudkit.spi
- powerlog.plxpclogger
- `security.ts.mobile-keybag-access`, `security.ts.webkit-client`
- FairPlay client 511712240

### com.apple.Music
- `FairPlay-Classic-Client` (legacy DRM)
- CommCenter fine-grained spi
- `pairingmanager.Read` / `.Write` / `.RemovePeer`
- payment.all-access + amp-card-enrollment
- `private.appstored`: Library / Purchase / IAPHistory
- `private.iad.background-client` + `privileged-client`
- `private.cfnetwork.har-capture-amp` (HTTP capture)
- `runningboard.jetengine` + sonic
- `hid.client.event-dispatch.internal`
- `security.assets.music.read-write`
- `telephony.cupolicy-rw-access`
- symptoms NetworkOfInterest + nw_activity.database
- `wallet.features.all-access`
- FairPlay client 1974055701
- keychain: apple / MediaRemote.pairing

### com.apple.MusicUIService
- `PairingManager.Read` / `.Write` / `.RemovePeer`
- `homekit.private-spi-access`
- `carkit.app`
- `telephonyutilities.callservicesd`: modify-calls / access-calls
- CarPlay hidden

### com.apple.measure — "Measure"
- `aned.private` (ANE)
- `pearl.iokit-user-access` (Face ID hardware)
- `camera.iokit-user-access`
- MobileGestalt JasperSerialNumber

### com.apple.mobilecal — "Calendar"
- generativeexperiences summarization / textcomposition / session
- `modelcatalog.full-access`, `modelmanager.inference`
- EntityResolution
- 9 IntelligencePlatform views
- MobileGestalt UniqueDeviceID

### com.apple.mobilemail — "Mail"
- `private.lockdown.finegrained-get: [DeviceCertificate, DevicePrivateKey]`
- `managedconfiguration.profiled-access`
- `MobileContainerManager.unrestrictedPersona`
- `usermanagerd.persona`: create / delete / fetch / background
- `icloudmailagent.secret.xpc`
- `finance.private`
- `network.socket-delegate` + networkserviceproxy
- 10 keychain groups
- Neural Engine IOKit
- `tailspin.dump-output`
- ProactiveSummarization, TextUnderstanding
- SystemConfiguration write
- `developer.mail-client`

### com.apple.mobilenotes — "Notes"
- `sage.summarization` + `sage.textcomposition`
- `modelmanager.assertion` + `forceAssetVersionSwitch` + `inference`
- `aned.private.ANEAccess.allow`
- GPU IOKit (AGXDeviceUserClient + IOSurfaceRootUserClient)
- Write paths: `/Documents/com.apple.mobilenotes/call_recordings/`, `/Library/CallServices/Recordings/`, `/Library/CallServices/Greetings/Recordings/`
- `TUUserActivityCreateCallRecording`, `TUUserActivityFinishedCallRecording`
- group.com.apple.GenerativePlayground
- keychain: group.com.apple.notes / apple / Markup / AnnotationKit

### com.apple.mobilephone — "Phone"
- `private.hid.client.service-protected`
- `private.icfcallserver`
- `springboard.proximity-active-bypass`
- `transparency.kt`
- `linkd.transcript.privileged`
- `private.imcore.spi.database-access`
- `telephonyutilities.callservicesd`: access-calls / modify-calls
- `siri.activation.service` + analytics.assistant
- Trial namespace SIRI_CARPLAY_JARVIS
- keychain: apple

### com.apple.mobilesafari — "Safari"
- `managedconfiguration.profiled.configurationprofiles: [UIInstallation]`
- `nfcd.hwmanager` + `nfcd.session.reader.internal`
- `launchservices.suppresscustomschemeprompt: *`
- `bluetooth.internal`
- `security.device.usb`
- `private.rsr-cryptex-access`
- `private.interstellar.data-access: *`
- 24 keychain groups (incl. lockdown-identities, password-manager, webkit.webauthn, safari.credit-cards)
- `private.associated-domains`
- `security.attestation.access`
- `developer.browser.app-installation`
- Writes `kCFPreferencesAnyApplication`
- `sage.summarization`, generativeexperiences

### com.apple.mobileslideshow — "Photos"
- `private.security.no-container`
- `private.kernel.panic`
- `private.lockdown.finegrained-get: [ActivationPrivateKey, DeviceCertificate]`
- `private.tcc.manager.access.delete: [kTCCServiceMediaLibrary]`
- `imagecapturecore.authorization_bypass`
- `security.network.server`
- `wifi.manager-access` + `wlan.authentication`
- `modelcatalog.full-access`, `modelmanager.inference`
- storage: Photos / PhotosLibraries
- `private.photos.service.internal.cloud`
- keychain: youtube.credentials / videouploadplugins / airplay / social.oauthurl / apple

### com.apple.mobilesms.compose — "MessagesViewService"
- `private.security.no-sandbox`
- `CommCenter.StormBreaker` (informal) + fine-grained (spi / cellular-plan)
- `imcore.spi.database-access` + `imdpersistence.database-access`
- ids.messaging alloy.biz / madrid / madrid.lite / madrid.lite.relay
- `sage.textcomposition` + `generativeexperiences.textcomposition` + `TextUnderstanding.SmartReplies.Inference`
- `dmd.policy` + `dmd.emergency-mode`
- `tcc.allow` (5 services)
- storage: AppDataContainers / Messages / Photos / PassKit / MobileDocuments
- GPU IOKit + ANE
- `wifi.manager-access`
- `interstellar.data-access: collaborations`
- `persona.read`
- screen-time + screentime-communication
- communicationsfilter, dprivacyd
- Writes `/Library/SMS/`, `/Library/CallHistoryDB/`, `/Library/MessagesMetaData/`

### com.apple.mobiletimer — "Clock"
- `healthkit.authorization_bypass`
- HID dispatch
- sleepd

### com.apple.musicrecognition — "Music Recognition (Shazam)"
- ShazamKit, corewifi, microphone

## N

### com.apple.NFCUISceneService
- `nfcd.background.tag.reading.extension`
- Minimal, hidden

### com.apple.NetworkEndpointPickerUI
- `avfoundation.background-camera-access`
- `avfoundation.capture.hidden-cameras.allow`
- `avfoundation.capture.nonstandard-client.allow`
- `rapport.Client`
- `sessionkit.permitMultipleProcessInputs`
- `DeviceAccess.private`
- multicast
- `sharing.airdrop.service`
- `Contacts.database-allow`
- TCC: Camera / Mic / AddressBook
- Shows views while locked

### com.apple.NewDeviceOutreachApp — "Coverage Details"
- `ndoagent`, `swc.system-app`
- `opensensitiveurl`, `openurlinbackground`
- Hidden, suspended launch; app-id prefix `0000000000.`

### com.apple.NewDeviceSetupUIService — "Setup"
- `managedconfiguration.profiled.set: Passcode`
- `bluetooth.discovery: MacSetup` (RSSI −45 dB; iPad / iPhone)
- `locationd.archived_authorization_decisions`
- `locationd.authorizeapplications`
- `findmydeviced.access`
- octagon
- screen-time
- `wifi.manager-access` + `wifi.internal`
- CoreAuthentication.SPI, LocalAuthentication.CallerName
- Shows views while locked

### com.apple.news — "News"
- ANE direct access
- payment.all-access + amp-card-enrollment + card-on-file
- MobileGestalt UniqueDeviceID
- `private.networkextension.configuration`
- `private.safari.can-use-launch-agent`
- `locationd.authorizeapplications`
- `private.ad.analytics` + `iad.unlimited-controllers-allowed` + `iad.opt-in-control`
- `private.associated-domains`
- CoreAuthentication.SPI, coreidvd.spi
- 18 CloudKit containers
- `hardware-button-service.event-consumption`
- `canModifyAppLinkPermissions`
- `NSPrivacyTrackingDomains: [b928de6b-…com]`

## P

### com.apple.PASViewService — "ProximityAppleIDSetup"
- `developer.in-app-identity-presentment`: jp-national-id-card / photo-id / us-drivers-license (+ elements: age, given/family-name, address, issuing-authority, doc-expiry/issue/number, driving-privileges, DOB)
- `provisioningUniqueDeviceID`
- `private.screen-time.persistence` + `screentime-setup`
- `payment.all-access`
- `PairingManager` Read / Write
- octagon, `bluetooth.system`
- `LocalAuthentication.DTO` + FallbackToNoAuth + ShortExpiration + Ratchet
- MobileGestalt: UniqueDeviceID / ProvisioningUniqueDeviceID
- Merchant: ams-identity-verification
- FairPlay client 511712240

### com.apple.PCViewService — "ProximityControlViewService"
- `CompanionLink`
- `ProximityControl.ProximityHandoffInteractions`
- `homekit.private-spi-access`
- `mediaremote.send-commands`
- `biome.read-only: App.Intent`
- `ProximityControl.server` + `remoteActivity`
- `secure-mode`, QuartzCore.secure-mode
- `springboard.hardware-button-service.event-consumption`
- Shared prefs (airplay / avfoundation / Home / music / ProximityControl / spotlightui / …)
- soundscapes.picker

### com.apple.PDUIApp — "PrivacyDisclosure"
- `PrivacyDisclosure.consentStore`
- backboardd
- `springboard.hardware-button-service.event-consumption`
- Writes `/private/var/mobile/Library/com.apple.PrivacyDisclosure/`
- Hidden, launchable during setup

### com.apple.Passbook — "Wallet"
- `apple-pay-trust.all-access`
- NFC: hwmanager / hce / ecommerce / peerpayment / reader / se / trust / assertion.handover / radio.powertoggle
- `nanoregistry.pairunpairobliterate`
- `mkb.usersession.keybagopaquedata` + info
- CommCenter fine-grained spi
- `contacts.database-allow`
- `finhealth.all-access`
- `managedconfiguration.profiled.set: Passcode + UserSettings`
- LocalAuthentication DTO + FallbackToNoAuth + PasscodeServices + RGBCapture + Storage
- `mobileinstall.xpc-services-enabled`
- `hid.client.event-dispatch.internal`
- `springboard.allowallcallurls`
- `telephonyutilities.callservicesd`: access-calls + access-call-providers
- `findmydeviced.access`
- Trial clients 820–824
- FairPlay client 87750944

### com.apple.PassbookSecureUIService
- NFC full stack (hwmanager / hce / ecommerce / peerpayment / reader / se / trust)
- seserviced (key / kmlXpcService / session / storage-management)
- `secure-mode`
- `openurlswhenlocked`, `requestDeviceUnlock`, `openurlinbackground`
- Shows views while locked, background audio

### com.apple.PassbookUISceneService — "Wallet"
- QuartzCore.system-layers
- `bannerkit.post`
- NFC stack (hwmanager / ecommerce / peerpayment / se / trust)
- `mkb.usersession.keybagopaquedata`
- `managedconfiguration.profiled.set: Passcode + UserSettings`
- `passes.add-silently`
- seserviced full
- keychain: PassbookUIService

### com.apple.PassbookUIService — "Wallet"
- Mirrors Passbook, plus:
- `systemconfiguration.SCPreferences-write-access: radios.plist`
- `networking.wifi-info`
- `nano.nanoregistry.pairunpairobliterate`
- `companionappd.connect.allow`
- `ids.messaging: madrid + urgent-priority`
- `springboard.mesa.unlockCredential`
- `hardware-button-service.background-event-consumption`
- `openurlswhenlocked`, `requestDeviceUnlock`
- `capture-button-restriction`
- FairPlay 87750944, Trial 820–824

### com.apple.Passwords
- 20+ keychain-access-groups (password-manager variants, webauthn, safari.history, recently-deleted, cfnetwork, sharing.safaripasswordsharing)
- `otpauth` + `apple-otpauth` URL schemes (TOTP handler)
- `authentication-services.access-credential-identities`
- `security.storage.Safari`
- `private.Safari.History`, `private.Safari.PasswordBreachHelper`
- `launchservices.changedefaulthandlers: otpauth`
- `hid.client.event-dispatch.internal`
- `corewifi.keychain`
- octagon
- App-id prefix `0000000000.`

### com.apple.PeopleMessageService — "Family Request"
- `keystore.absinthe` + `sik.access`
- `peopleMessage` URL scheme
- `contacts.database-allow`
- `screentime-ask`
- `biome.read-only: AskToBuy / ScreenTimeRequest`
- FairPlay client 511712240

### com.apple.PeopleViewService — "Contacts"
- FindMy friendship / location / settings
- CallHistoryDB read, SMS read, MessagesMetaData read
- NeuralEngine IOKit
- CoreDuet people
- imdpersistence db, contacts db
- TCC: AddressBook / Camera / Mic / Photos / FaceID
- mediaanalysisd
- `people://` URL scheme

### com.apple.Photos.PhotosUIService
- SensitiveContentAnalysis intervention host
- biome writer (4 SCA streams)
- `system-keychain`
- restrictionspassword read-write
- `ManagedSettings.effective-read`
- screen-time, opensensitiveurl
- keychain: apple

### com.apple.PosterBoard
- DND full lifecycle (assertion / modeconfig / settings / state)
- `runningboard.terminateprocess` + `launchprocess`
- `hid.event-dispatch.internal`
- appstored Library + Install
- homeScreenLayout, wallpaper get/set, icon visibility changes
- application removability proxy
- status-bar-overrides
- network client
- AppDataContainers storage

### com.apple.PreBoard
- `private.security.no-sandbox`
- `allow-obliterate-device`
- `kernel.darkboot`, jetsam
- `launchd.reboot` + `app-server`
- `CommCenter.Preferences-delete`
- keystore device + verify + stash
- `mkb` keybagopaquedata + info
- AMFI commit-profile + developer-mode-control + set-trust
- AppleCredentialManager preboard.config
- biometrickit match, BMK
- IDS registration-reset
- IOKit: IOAV / IOMobileFramebuffer / IOSurface / RootDomain / AGX / IOGPU / AppleCredentialManager / AppleKeyStore / AMFI
- `wifi.manager-access`
- Shows views while locked

### com.apple.Preferences — "Settings"
- `private.security.no-sandbox`, `no-container`, `platform-application`
- `security.storage-exempt.heritable`
- `nvram.boot-args-set-allow`
- `kernel.darkboot`, `kernel.jetsam`
- AMFI set-trust + remove-trust + commit-profile + schedule-profile + set-csp
- `launchd.reboot` + `userspace-reboot`
- `CommCenter.StormBreaker` (informal) + fine-grained (15 sub-entitlements)
- `healthkit.authorization_bypass` + authorization_manager read/write/reset + medicaliddata + obliteration + feature-availability.read-write-any
- `tcc.manager` (full) + `tcc.allow` (16 services incl. MicrophoneInjection)
- `managedconfiguration.profiled.configurationprofiles: CloudLockedRemoval` + set ClientRestrictions/Passcode + provisioningprofiles Removal + get MDMInfo + mdmd-access + mdmd.push + teslad-access
- `lockdownmoded.read-write`
- LocalAuthentication (full: incl. ExtractCredential / SaveExtractableCredential / RGBCapture / PasscodeServices)
- CoreAuthentication.SPI, authentication-services (full)
- in-app-identity-presentment, coreidvd (full)
- `wipedevice` + `springboard.wipedevice`
- `coreaudio.CanRecordPastData` + CanRecordWithoutSessionActivation + register-internal-aus + borrowaudiosession
- nfcd (hwmanager / radio.powertoggle / reader.internal / se / trust)
- seld.tsmmanager, seserviced (full)
- payment (full) + `softposreaderd.provision`
- PairingManager (full)
- ids.nearby + registration-control + registration-reset
- nearbyinteraction.privileged + device-presence
- bluetooth.system + custom.properties.writable
- airdrop.settings, rapport.people
- appstored (install / install-system / demote / private / xpc)
- mobileinstall SPI (Install / Uninstall / CopyDiskUsage FLS)
- dmd.operation.* (fetch-apps / remove-app / start-managing-app)
- FindMy (full), searchpartyd
- `nanoregistry.pairunpairobliterate`
- 40+ keychain groups incl. `keychain-cloud-circle`, `modify-anchor-certificates`, `system-keychain`
- generativeexperiences + modelcatalog + modelmanager + `privatecloudcompute.admin`
- biome (many streams)
- IOKit (30+ user client classes)
- `sensorkit.export.allow-all` + `reader.wildcard.allow`
- Trial (20 client IDs)
- `lockdown.reset-pairing` + `unpair`
- `vfs.snapshot` + `snapshot.user`
- corerepair.* , replicator.controller, `uarp.endpoint.control`
- osanalytics, eligibilityd.*, safetyalerts.spi, securebackupd.access, logd.admin, tailspin.config-apply

### com.apple.Preview
- `UAF.FM.GenerativeModels` + Overrides
- modelmanager
- biome writer (GenerativeModels instrumentation)
- spotlight exattrs
- DocumentWorkflowsService, print
- TCC: Camera
- `platform-application`

### com.apple.PreviewShell — "Xcode Previews"
- `private.chrono-extension-host`
- `oop-jit.loader: previews` (JIT)
- `runningboard.hereditarygrantoriginator`
- `springboard.homeScreenIconStyle`
- Icon visibility control

### com.apple.ProximityReaderSceneUI — "Tap to Pay on iPhone"
- `nfcd.assertion.handover` + hwmanager
- `coreaudio.CanRecordWithoutSessionActivation`
- `private.passkit.pass-presentation-suppress-from-background`
- TCC: FaceID / Camera / AddressBook
- Hidden, launches during setup

### com.apple.ProximityReaderUIService
- Mirrors ProximityReaderSceneUI
- IOKit: IOSurfaceRootUserClient
- Hidden, background execution

### com.apple.PublicHealthRemoteUI — "ExposureNotificationRemoteViewService"
- developer / private `exposure-notification` + test
- Continuous BG mode
- CA developer region

### com.apple.purplebuddy — "Setup" (Setup Assistant)
- `private.security.no-sandbox`, `security.system-container`
- `private.lockdown.finegrained-get`: DevicePrivateKey, DeviceCertificate, BrickState, ActivationInfo, ActivationState, SetupState, RestoreState
- `private.lockdown.finegrained-set`: SetupState, RestoreState, DeviceName, ActivationStateAcknowledged
- `private.lockdownmoded.read-write`
- `managedconfiguration.profiled.configurationprofiles`: DEPInstallation, SilentNonUIInstallation, Removal, CloudLockedRemoval
- managedconfiguration: mdmd-access, mdmuserd-access, profiled-access, teslad-access
- `wipedevice`
- `frontboard.shutdown`
- `springboard.lockDevice`, presentPowerDownUI, disallowControlCenter, disallowNotificationCenter
- `private.vfs.snapshot` + `snapshot.user`
- LocalAuthentication: DTO, DTO.FallbackToNoAuth, PasscodeServices, Storage (incl. BiometricLivenessFlag, SetDSLModeEnabled, SetDSLStrictModeEnabled)
- biometrickit: allow-config / allow-enroll / allow-id-mgmt / allow-match
- NFC: hwmanager, info, session.se, session.trust, `internal.nfc.allow.backgrounded.session`
- seserviced: all.endpoints.and.cas, fido; seld.cm, seld.tsmmanager
- BTServer: allowRestrictedServices, appleMfgDataScanner, programmaticPairing, supportsPairing
- keystore: auth-token, device, device.verify, lockassertion (+global_assertion, restore_from_backup), sik.access, stash.access, stash.persist
- `private.system-keychain`, `keychain-cloud-circle`, `private.keychain.sysbound`
- keychain-access-groups (12): apple, identities, appleaccount, preferences, certificates, VideoSubscriberAccount, lockdown-identities, airplay, ProtectedCloudStorage, passd, Sharing, cdp.rk
- `private.applesmc.user-access` + AppleSMCClient IOKit
- `SystemConfiguration.SCDynamicStore-write-access` + `SCPreferences-write-access` (preferences.plist, AutoWake.xml, radios.plist, jetsam.plist, virtualMemoryMode.plist, OSThermalStatus.plist)
- CommCenter fine-grained: cellular-plan, spi, data-allowed-write
- `private.octagon`, cdp.recovery / recoverykey / walrus / statemachine / followup
- coreidvd (digital-presentment + firstpartyclient + merchants)
- in-app-identity-presentment (jp-national-id-card / photo-id / us-drivers-license + elements)
- `os-eligibility-domain.change.molybdenum`
- `private.mobilestoredemo.enabledemo`: Enroll, Manage
- `private.mobileinstall.allowedSPI`: Install, Uninstall, FetchListOfAppsRequiringPreInstallConsent
- `softposreaderd.provision`
- `logd.admin`, `private.webinspector.allow-remote-inspection`
- `nano.nanoregistry.pairunpairobliterate`
- `passes.add-silently`
- payment / peerpayment all-access, in-app-payments, cards.all-access
- coreaudio CanRecordPastData + CanRecordWithoutSessionActivation + register-internal-aus + borrowaudiosession
- FindMy device access, `private.persona.read` / `.write`
- `private.tcc.allow`: AddressBook, Photos, Camera, Microphone, MediaLibrary, Willow, Liverpool, BluetoothAlways, FaceID
- `wifi.manager-access`
- `security.attestation.access`
- `private.seeding.client`
- (This bundle carried by far the largest set; ~247 keys reported. Above is the high-signal subset as captured.)

## R

### com.apple.RecoverDeviceUI — "Recover Device UI extension"
- `PairingManager.HomeKit` + Read / Write
- `bluetooth.discovery: OSRecoveryExtended` (RSSI −45 dB)
- `coreaudio.CanRecordWithoutSessionActivation`
- `asset.change-daemon-config`

### com.apple.RemotePassUIService — "RemotePaymentPassActionsService"
- `SBBehavesAsCaller`
- payment.all-access
- `contacts.database-allow`
- TCC: AddressBook
- Hidden, launches during setup, background audio

### com.apple.RemoteiCloudQuotaUI
- `private.accounts.bundleidspoofing`
- `billing.all-access`
- `photos.service.internal.cloud`
- `LocalAuthentication.DTO.FallbackToNoAuth`
- FaceID
- FairPlay client 1445028844, hidden

### com.apple.reminders — "Reminders"
- `private.activitykit.bypassAuthorizationUI`
- `private.cloudkit.masquerade`
- `private.remindd` (debug: true)
- `private.imcore.imagent`
- `private.replicator.dataProvider`
- `runningboard.launchprocess`
- `rootless.storage.coreduet_knowledge_store`
- `proactive.eventtracker`
- donotdisturb full control (as com.apple.focus.activity-manager)

### com.apple.replaykitangel — "ReplayKitAngel"
- Frame capture receiver
- Remote alerts
- Video conferencing

## S

### com.apple.SESUIServiceApp — "Storage Management"
- `surfboard.application-service-client`
- payment.all-access + peerpayment.all-access
- Hidden, launches during setup, secure-mode

### com.apple.SIMSetupUIService — "Cellular (SIM/eSIM Setup)"
- `bluetooth.discovery: SIMTransfer / 2 / 3` (RSSI −47 dB, screenLocked: true)
- CommCenter fine-grained: cellular-plan / identity / spi
- `imagent.embedded.auth`
- keychains: identities / coretelephony / lockdown-identities

### com.apple.SOSBuddy — "Connection Assistant"
- `CommCenter.StormBreaker` (informal) + fine-grained connection-assistant
- `locationd.eed_emergency_contact_names`
- `healthkit.medicaliddata`: read-write
- SOS contacts, critical alerts
- Background location / audio modes

### com.apple.SafariViewService — "Safari"
- `Safari.History` + `PasswordBreachHelper`
- `authentication-services.app-passkey-autofill`
- `mobilesafari.security.storage`
- WebClips read-write
- `changeDefaultHandlers`: http / https / otpauth
- `suppressCustomSchemePrompt: *`
- `temporary-sbpl` (WebKit microphone / camera extensions)
- `hardened-process`
- 25+ keychain groups
- `canLoadAnyContentBlocker`
- `associated-domains: true`
- webpush + `webinspector.proxy-application`
- `privacy.dprivacyd.allow`
- `managedconfiguration.profiled: UIInstallation`

### com.apple.SafetyMonitorApp — "Check In"
- `carousel.liveactivities.prevents_smartstack_dismissal`
- `openurlswhenlocked`
- CoreRoutine SafetyMonitor access

### com.apple.ScreenContinuityShell
- `private.hid.client.admin`
- `accessibility.api`
- `replicator.controller`
- `videoconference.allow-conferencing`
- `springboard.continuitysession`

### com.apple.ScreenSharingViewService
- `videoconference.allow-conferencing`
- `screensharing.xpcaccepted`
- `callservicesd: access-calls`
- Hidden, secure-key window

### com.apple.ScreenTimeUnlock
- `private.screen-time`
- MobileGestalt UniqueDeviceID
- Hidden, continuous BG

### com.apple.ScreenTimeWidgetApplication — "Screen Time"
- Minimal (widget container)

### com.apple.ScreenshotServicesService — "Screenshots"
- `modelcatalog.full-access` + `modelmanager.inference`
- `visual-intelligence.ui.paths`
- `sysdiagnose.read-write`
- `feedback.drafting`
- generativeexperiences: session / summarization / textcomposition
- biome: VisualIntelligenceCamera events
- keychain: apple / openai / markup / annotationkit

### com.apple.SharedWebCredentialViewService
- IOKit: AGXDevice (full stack)
- `associated-domains: true`
- Hidden

### com.apple.Sharing.AirDropUI — "AirDrop"
- `ProximityControl.ProximityHandoffInteractions`
- `sociallayer.highlights` + `shareable-content`
- `messages.collaboration-initiate-send`
- `callservicesd`: access-calls + modify-calls
- biome writer (SCA flows)
- Hidden, background audio

### com.apple.SharingUIService
- `hid.client.event-dispatch.internal`
- runningboard launchprocess + trustedtarget
- iTunes private lookup
- contacts
- TCC: AddressBook / Photos / MediaLibrary
- QuartzCore global-capture

### com.apple.SharingViewService — "Setup"
- coreaudio: CanRecordPastData + CanRecordWithoutSessionActivation + register-internal-aus
- payment (full)
- `PairingManager.HomeKit` + Read + Write
- `CompanionLink`
- bluetooth.system + BluetoothServices + cloud
- wifi.eap-nearby-device-setup-config-copy + manager-access
- `wirelessproxd-disable-scans`
- `backboardd.proximityDetection`
- `ProximityAppleIDSetup.account-picker-host`
- sharing: DeviceDiscovery + RemoteInteractionSession + Session + Services
- coreidvd.digital-presentment + firstpartyclient
- keystore.absinthe + sik.access; absinthe-client 355968556; adi-client 821141022
- FindMy: friendship / location / settings
- searchpartyd: accessorydiscovery + beaconmanager + pairingmanager
- accounts: appleaccount.fullaccess + idms.fullaccess + allaccounts
- MobileGestalt protected keys (UniqueChipID / UniqueDeviceID / SerialNumber / WifiAddress / BootManifestHash, etc.)
- preboot + factorydata access
- CommCenter fine-grained: identity / cellular-plan / spi
- appstored.install-apps + install-system-apps; mobileinstall InstallForLaunchServices
- `homekit.private-spi-access` + `remote-login.private`
- `system-keychain`
- screen-time (full)
- telephonyutilities.callservicesd
- `networkextension.configuration`
- octagon
- 9 keychain groups, `platform-application`
- FairPlay client 1445028844
- IOTimeSync IOKit

### com.apple.ShazamEventsApp — "Events"
- CommCenter spi
- accounts fullaccess
- corewifi, NetworkOfInterest
- shazamd XPC

### com.apple.ShortcutsUI — "Shortcuts"
- `modelcatalog.full-access` + `modelmanager.inference`
- generativeexperiences session
- `systemgroup.configurationprofiles`
- `managedconfiguration.profiled-access`
- posterboard data-store: mutate / delete
- runningboard.assertions: shortcuts + siri + angeltarget
- 3 app groups
- TCC (11 services)
- opensensitiveurl
- `platform-application`

### com.apple.SleepLockScreen
- `healthkit.authorization_bypass`
- `locationd.prompt_from_background` + usage_oracle
- `nano.nanoregistry.generalaccess`
- IOKit: RootDomainUserClient
- Shows views while locked
- FairPlay client 511712240

### com.apple.Spotlight
- `private.security.no-container`, `platform-application`
- `private.tcc.manager.read.access: kTCCServiceAll`
- storage: AppDataContainers, Messages, MessagesMetaData, PhotosLibraries, MobileDocuments, SiriInference, triald
- `private.CallHistory.read`, `private.Safari.History`
- `intelligenceplatform`: EntityResolution + Knosis (informal) + View (+ indexes + 15 views)
- proactive: ActionPrediction + AppPrediction + PersonalizationPortrait (Contact / NamedEntity / Topic)
- `hid.client.event-dispatch.internal`
- GPU IOKit (full) + ANE + JPEG
- biome (25+ read streams incl. accessibility states)
- `apfs.unlock`
- `kernel.override-cpumon`
- `mobileinstall.allowedSPI: UninstallForLaunchServices`
- `systemgroup.configurationprofiles`, `managedconfiguration.profiled-access`
- `dmd.emergency-mode` + `dmd.policy`
- contacts + contactsui + corerecents
- messages.imcore + imcore.spi.database-access
- fileprovider: enumerate + fetch-url + extension-host
- persona.fetch + observer
- coreduetd.allow + context + people
- Trial 332–337 / 409 / 753 / 755
- FairPlay 511712240
- network client + socket-delegate
- `hardened-process`
- shortcuts: background-running + stepwise-execution + variable-injection

### com.apple.SpringBoardEducation
- QuartzCore secure-mode + vends-view-services
- Hidden

### com.apple.StickerKit.StickerPickerService — "Emoji Keyboard"
- `modelcatalog.full-access` + `modelmanager.inference` + `forceAssetVersionSwitch`
- Reads `.GlobalPreferences.plist`, MobileSMS caches, Keyboard `stkusage.dat`
- TCC: Camera / Photos / AddressBook
- `messages.sticker-sharing-level: system`
- GPU IOKit
- GenerativePlayground group
- `assetsd.xpcstore_restricted`: photos.person / photos.face
- IntelligencePlatform views
- Reads `eligibility.plist`

### com.apple.StoreDemoViewService — "Store Demo"
- `private.mobilestoredemo.enabledemo: Manage`
- `platform-application`
- Shows views while locked

### com.apple.StoreKitUISceneService — "StoreKit UI"
- StoreKit client-override
- MobileGestalt UniqueDeviceID
- AppleMediaServices

### com.apple.SubcredentialUIService — "Wallet"
- `SBBehavesAsCaller`
- `passes.add-silently`
- payment.all-access + externalized-context
- Attributed identity: com.apple.Passbook
- `platform-application`, background audio, shows views while locked

### com.apple.SupportFlow — "Step-by-Step Help"
- `managedclient.configurationprofiles`
- `networkextension.configuration`
- biome: DeviceExpert.Troubleshooting
- generativeexperiences (availabilityService + waitlistStatus)
- payment all-access
- ids.registration: ess + madrid
- CoreAuthentication SPI
- mobileactivationd device-identifiers + spi

### com.apple.SystemPaperViewService — "System Paper"
- vends-view-services
- Live Activities support (minimal)

### com.apple.SystemVoiceAssistant — "Siri Assistant"
- `frontboard.shutdown`
- `runningboard.terminateprocess` + `terminatemanagedprocesses` + `launchprocess`
- `managedconfiguration.profiled-access`
- `launchservices.changedefaulthandlers`: assistant + side-button
- activitykit: canBypassActivityCountLimits + ephemeralActivityRequester + unboundedActivityRequester
- `tcc.manager.access.read: Camera`
- Shows views while locked

### com.apple.shortcuts — "Shortcuts"
- `developer.networking.networkextension`: app-proxy-provider + content-filter-provider + packet-tunnel-provider
- `nfcd.hwmanager` + `session.reader.internal`
- `bluetooth.system`
- `managedconfiguration.profiled-access`
- developer.homekit + background-mode + private.homekit + private-spi-access + shortcuts-automation-access
- `private.tcc.allow` (11 services)
- `private.appintents-attribution-override`
- `linkd.transcript.privileged`
- `runningboard.terminateprocess`
- `sirittsd.can-dump-audio`
- `systemactions.client`
- `security.system-groups`: configurationprofiles
- springboard: addWebClipToHomeScreen + removeWebClipFromHomeScreen + webClipService
- `private.email`, `private.translation`
- `NSAllowsArbitraryLoads: true`
- `modelcatalog.full-access` + `modelmanager.inference`
- keychain: com.apple.openai

### com.apple.shortcuts.runtime — "ShortcutsViewService"
- `configprofiles` system group
- TCC (11 services)
- `profiled-access`
- Privileged transcripts

### com.apple.sidecar — "Continuity"
- `frontboard.debugapplications`
- `springboard.lockDevice`
- `sidecar-relay.presenter`
- `springboard.secureAppAssertion`
- `hardware-button-service.event-consumption`
- Continuous BG mode

### com.apple.siri — "Siri"
- `private.tcc.manager.access.modify: [kTCCServiceSiri]`
- `private.tcc.manager.access.read: [kTCCServiceAll]`
- keychain: com.apple.openai
- `keystore.device`
- `generativeexperiences.ExternalPartnerCredentialStorage`
- `runningboard.terminateprocess` + `endowment-originator`
- `assistant.security`
- `private.appintents-attribution-override`
- `private.replay-kit`
- corespeech.corespeechd.xpc + voicetriggerservice
- HID event monitor + dispatch
- intelligenceplatform: EntityResolution + View
- `siri.analytics.assistant`: stream.unifiedMessageStream.readonly
- Reads `MDMAppManagement.plist` (configurationprofiles system group)
- IOKit: AppleSPUHIDDriverUserClient
- 6 TCC services, 23 trial namespaces, 5 group containers

### com.apple.social.SLYahooAuth — "SLYahooAuth"
- Framebuffer only

### com.apple.stocks — "Stocks"
- `mobileactivationd.spi`
- MobileGestalt UniqueDeviceID
- `networkextension.configuration`
- AppleInternal read

### com.apple.susuiservice — "SoftwareUpdateUIService"
- `private.security.no-container`
- `keystore.device` + `stash.access`
- `mkb.usersession.info` + `keybagopaquedata`
- `MobileContainerManager.otherIdLookup`
- `springboard.activateRemoteAlert`
- `SBIsLaunchableDuringSetup: true`
- GPU IOKit + RootDomainUserClient
- `platform-application`, system-container

### com.apple.systemactions — "SystemActions"
- `developer.networking.networkextension`: app-proxy-provider + content-filter-provider + packet-tunnel-provider
- `private.shazamkit.allow-external-audio-recording` + `allow-internal-audio-recording`
- `private.mediaexperience.allowrecordingtemporarily`
- `Pasteboard.background-access` + `paste-unchecked` + `trusted-bundle-layout`
- `frontboard.shutdown`
- CommCenter fine-grained: cellular-plan / data-usage / preferences-write / spi
- `managedconfiguration.profiled-access`
- `private.homekit` + `allow-secure-access`
- `private.corewifi` + bssid
- `private.iokit.batterydataprecise`
- `springboard.flash-color`
- `private.mediaexperience.setsilentmode.allow`
- `sirittsd.can-dump-audio`
- TCC (11 services)
- `security.system-groups`: configurationprofiles
- `modelcatalog.full-access` + `modelmanager.inference`
- biome read-write (20+ streams)

## T

### com.apple.TDGSharingViewService — "TDG Sharing"
- `managedconfiguration.profiled.configurationprofiles`: SilentNonUIInstallation + Removal
- `healthkit.authorization_bypass`
- `healthkit.metadata.private`
- `healthkit.read_authorization_override: HKVisionPrescriptionTypeIdentifier`
- `systemgroup.configurationprofiles`
- `findmydeviced.access`
- `locationd.archived_authorization_decisions`

### com.apple.TVAccessViewService — "TV Access"
- WatchList surfboard chrome customization
- `/Library/com.apple.WatchListKit/`

### com.apple.TVRemoteUIService — "TV Remote"
- `nearbyinteraction.privileged` + `device-presence` + background
- `coreaudio.app-tap`
- Microphone TCC
- `hardware-button-service.event-consumption`
- Siri activation assertions
- System apertures (Dynamic Island)

### com.apple.TVSetupUIService — "Apple TV Setup"
- `captive.private`
- `homekit.private-spi-access` + `remote-login.private`
- `networkrelay.deviceMonitor` + devices.read / write
- `PairingManager.HomeKit` Read / Write
- `wifi.eap-nearby-device-setup-config-copy`

### com.apple.Translate — "Translate"
- `aop.hid-driver.user-client`: eclipse send-command
- `hid.system.user-access-service`
- `springboard.lockDevice`
- `CloudSubscriptionFeatures.gm.bypass`
- CloudSubscription optIn / optOut
- `hid.client.event-dispatch.internal`

### com.apple.TrustMe — "TrustMe"
- IOKit: IOSurface / AGXDevice / IOMobileFramebuffer
- Setup launchable
- Continuous BG mode

### com.apple.tips — "Tips"
- MobileGestalt UniqueDeviceID
- Camera capability
- datamigrator

### com.apple.tv — "TV"
- `private.FairPlayIOKitUserClient.access` + FairPlayIOKit IOKit class
- payment.all-access + amp-card-enrollment + card-on-file + `passes.add-silently`
- `keystore.device`
- coreidvd.spi
- ids: phone-number-authentication + registration + session + remoteurlconnection
- `launchservices.suppresscustomschemeprompt: *`
- `visioncompaniond.client`
- in-app-payments

## U

### com.apple.UIKit.ColorPickerUIService — "Color Picker"
- Eyedropper daemon service
- secure-mode

### com.apple.UIKit.FontPickerUIService — "Font Picker"
- User fonts enumeration
- fontservicesd
- FontPickerStorage preferences write

## V

### com.apple.VSViewService — "Video Subscriber Account"
- `tcc.manager.access.read: kTCCServiceAll`
- `tcc.manager.access.modify: kTCCServiceMSO`
- `webinspector.allow-remote-inspection`
- systemgroup: VideoSubscriberAccount
- FairPlay client 1700658526

### com.apple.VoiceMemos — "Voice Memos"
- `tcc.manager.access.read: kTCCServiceAll`
- `tcc.manager.access.modify: Liverpool`
- `tcc.manager.access.delete: Liverpool`
- Shows views while locked
- `platform-application`, system-application
- FairPlay client 511712240

## W

### com.apple.WebContentFilter.remoteUI.WebContentAnalysisUI — "WebContentRestrictionsUI"
- screen-time access
- keychain: apple / preferences
- Shared-preference read-only: SpringBoard

### com.apple.WebSheet — "WebSheet"
- `captive.private`
- `developer.web-payments`
- `authentication-services.access-credential-identities` + `allow-authentication-request-any-rpid`
- managedconfiguration UI installation
- opensensitiveurl: prefs WIFI + Safari tabs
- 19+ keychain groups
- `hardened-process`

### com.apple.WorkoutRemoteViewService — "Workout Remote View Service"
- `healthkit.authorization_bypass`
- `fitnessintelligenced` access
- nano nanoregistry
- Shows views while locked

### com.apple.WritingToolsUIService — "Writing Tools"
- generativeexperiences: session / summarization / textcomposition + `ExternalPartnerCredentialStorage` + feedback.drafting
- `modelmanager.inference`
- `sage.summarization` + `sage.textcomposition`
- keychain: com.apple.openai
- `runningboard.launchprocess` + trustedtarget
- `userprofiles.read`
- `guest-user-mode-client`

### com.apple.weather — "Weather"
- `locationd.clearauthorizations`
- `UNAllowCriticalAlerts`
- MobileGestalt UniqueDeviceID
- `data-usage-classification-override`
- carrier-constrained networking
- SystemConfiguration SCPreferences read: radios.plist

### com.apple.webapp — "Web"
- install / uninstall coordination
- WebClips read-write
- `suppresscustomschemeprompt: *`

## Accessibility / Angel / Chrono / misc

### com.apple.accessibility.AccessibilityReader — "Accessibility Reader"
- `accessibility.api` + voiceover
- `runningboard.accessibility`
- `requestAppSwitcherAppearanceForHiddenApp`
- opensensitiveurl

### com.apple.accessibility.MagnifierAngel — "Live Recognition"
- `accessibility.voiceover`
- `aned.private.ANEAccess.allow`
- appleneuralengine + private.allow
- HID: event-filter + event-dispatch + event-monitor + service-protected
- `security.storage.Photos`
- `biome.read-write`: Instrumentation
- background-camera-access + capture.allow
- Shows views while locked, ephemeral activity requester

### com.apple.appleseed.FeedbackAssistant — "Feedback Assistant"
- `managedconfiguration.profiled-access`
- MobileGestalt UniqueDeviceID
- security.storage: Notes + Safari
- ProactiveSummarization: summarization + model-input + feedback
- `platform-application`

### com.apple.avkit.AVKitRoutingService — "AVKit Routing"
- Microphone TCC
- Media routing (minimal)

### com.apple.calculator — "Calculator"
- `runningboard.terminateprocess`
- Shows views while locked, system-application

### com.apple.camera — "Camera"
- `private.security.no-container`
- `nfcd.assertion.handover` + `nfcd.hwmanager`
- CommCenter fine-grained: spi + public-cellular-plan + public-esim-qr-code
- photos.service.internal.cloud + library + resource
- `sharing.DeviceDiscovery`
- `wifi.manager-access`
- `barcodesupport.allowNotifications`
- `contacts.database-allow`
- SensitiveContentAnalysis client
- `platform-application`, secure-mode

### com.apple.chrono.AccessoryLiveActivities-AuthorizationAppSheet
- Activity authorizer, chronoservices, hidden

### com.apple.chrono.WidgetRenderer-Activities / -CarPlay / -Default / -WatchFaces
- `healthkit.authorization_bypass`
- nano nanoregistry
- Shows views while locked
- `platform-application`

### com.apple.compass — "Compass"
- Carrier-constrained location (hiking category)
- Location access

---

## Cross-reference: capability → apps (as reported)

Quick pivot index. Same reliability caveats apply.

- **no-sandbox / no-container:** CheckerBoard, Device-Recovery-Assistant, HeadphoneProxService, PreBoard, Preferences, Spotlight, mobilesms.compose, purplebuddy, susuiservice, Home.HomeUIService, camera, mobileslideshow, facetime (`app-sandbox:false`)
- **NVRAM write / boot-args:** CheckerBoard, Device-Recovery-Assistant, Diagnostics, Preferences (boot-args-set), PreBoard (darkboot)
- **kernel.panic:** mobileslideshow
- **lockdown fine-grained key access:** purplebuddy (get+set), mobilemail (get), mobileslideshow (get)
- **lockdownmoded read-write:** Preferences, purplebuddy
- **MDM profile install/remove:** purplebuddy (DEP + silent + cloud-locked removal), TDGSharingViewService (silent install + removal), Preferences (cloud-locked removal), mobilesafari (UI install), HDSViewService (removal), Home (queue), DocumentsApp (UI install)
- **MDM profiled-access:** mobilemail, ios.StoreKitUIService, podcasts, ShortcutsUI, shortcuts, systemactions, SystemVoiceAssistant, appleseed.FeedbackAssistant, MobileStore, MailCompositionService
- **CommCenter StormBreaker (informal):** Health, InCallService, MobileSMS, mobilesms.compose, Preferences, SOSBuddy
- **all 3 network extension types:** shortcuts, systemactions
- **NFC hwmanager / SE / trust:** purplebuddy, mobilesafari, shortcuts, camera, Passbook family, Bridge, Diagnostics, CredentialSharingService, AMSEngagementViewService, HDSViewService
- **TCC manager read ALL:** Health, MomentsUIService, Spotlight, VSViewService, VoiceMemos, siri
- **TCC manager modify / delete:** VSViewService (modify MSO), VoiceMemos (modify+delete Liverpool), mobileslideshow (delete MediaLibrary), siri (modify Siri)
- **HealthKit authorization_bypass:** Fitness, Health, HealthPrivacyService, MomentsUIService, Preferences, SleepLockScreen, TDGSharingViewService, WorkoutRemoteViewService, chrono.WidgetRenderer (×4), mobiletimer
- **audio recording (past/systemwide/internal+external):** Home family, HDSViewService, HeadphoneProxService, ContinuitySingShieldUI, InCallService, MediaRemoteUI/Service (SystemWideTap), SharingViewService, ProximityReaderSceneUI, RecoverDeviceUI, systemactions (internal+external), TVRemoteUIService (app-tap)
- **device wipe / shutdown / lock:** purplebuddy (wipe/shutdown/lock), Preferences (wipe), systemactions (shutdown), SystemVoiceAssistant (shutdown), sidecar / Translate (lock)
- **process termination:** PosterBoard, calculator, SystemVoiceAssistant, shortcuts, siri, runningboard consumers
- **OpenAI keychain group:** shortcuts, siri, WritingToolsUIService, ScreenshotServicesService
- **generative AI (sage / modelcatalog / modelmanager):** MobileSMS, mobilesms.compose, Preferences, Preview, ScreenshotServicesService, ShortcutsUI, shortcuts, StickerPickerService, Spotlight, SupportFlow, WritingToolsUIService, mobilenotes, mobilemail, mobilecal, journal, mobilesafari, mobileslideshow, systemactions
- **bundle-id spoofing:** RemoteiCloudQuotaUI, icq
- **Neural Engine (ANE) direct:** MagnifierAngel, measure, mobilenotes, news, mobilemail (IOKit), facetime (IOKit)
- **FairPlay IOKit hardware:** iBooks, tv, ContinuitySingShieldUI
- **debug other apps:** sidecar, freeform
- **nanoregistry pair/unpair/obliterate:** Bridge, Diagnostics, Fitness, Passbook, PassbookUIService, Preferences, purplebuddy

---

## Changelog / notes for maintainers

- v1.0 — Initial consolidation from source transcript. Fabricated appendix excluded. ~180 named bundles.
- **Verify before publishing.** Recommend re-deriving from raw `all_apps.json` and diffing against this file. Any entitlement here not present in the raw dump should be dropped; anything in the raw dump not here should be added.
- Informal labels to confirm against real keys: "StormBreaker," "Knosis," "Liverpool," "MSO."
