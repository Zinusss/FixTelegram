# FixTelegram (iOS Sideload Fix)

Standalone iOS dynamic library (`arm64`) to fix sideloading crashes in Telegram and Ghostgram on non-jailbroken devices (free Apple Developer accounts).

## What it fixes:
1. **Black screen / crash on launch**: Redirects `[NSFileManager containerURLForSecurityApplicationGroupIdentifier:]` to `<Documents>/AppGroup`.
2. **Crash on SMS code / 2FA login**: Hooks `SecItemAdd`, `SecItemCopyMatching`, `SecItemUpdate`, and `SecItemDelete` via `fishhook` and `__DATA,__interpose` to strip `kSecAttrAccessGroup`.

## How to use:
Inject `FixTelegram.dylib` or `SideloadFix.dylib` into the Telegram IPA using **Sideloadly**, **TrollStore**, **AltStore**, **Scarlet**, or **Esign**.
