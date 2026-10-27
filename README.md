# Pimatech Gage Block Stack Resolver

A free, open-source Android tool that finds the blocks needed to make a requested dimension from your available inventory. Starts with a common 81-piece inch or 87-piece metric set and lets you mark missing blocks unavailable, add extra physical blocks (including duplicate sizes), edit sizes, or remove rows.

## Download

See Releases for the Android APK and matching complete source archive. Version 1.0.0 is a **development preview**, signed with a retained development certificate, not a production or Google Play release. Android 8.0 or newer. Installs separately from Pimatech Ball Drop and Sine Bar. Runs offline, without accounts, ads, subscriptions, analytics or Internet permission.

Download the APK on Android, open the file, and allow the downloading browser or Files app to install unknown apps if prompted. Check your inventory and a known stack before use. Example: 2.4321 in resolves to 2.00000 + 0.20000 + 0.13200 + 0.10010 in.

## How it resolves

The solver minimizes nominal height error, then block count, then height. An exact stack always wins over every approximate stack; among exact stacks, the fewest physical blocks are selected. If an exact stack is impossible, the result is clearly marked CLOSEST / NOT EXACT with the signed difference (stack minus requested).

Each physical inventory row may be used only once. Duplicate sizes require duplicate physical blocks. Zero/no blocks is an eligible height. Exact decimal/integer arithmetic avoids silent rounding of a requested dimension. There is no five-block shortcut. Maximum inventory: 128 rows; oversized searches receive an explicit no-result message rather than a partial answer.

Each preset keeps its own requested dimension and customized inventory. Changing sets recalls the saved setup instead of converting a dimension. Inch custom blocks support 5 decimals; metric blocks support 4; requested dimensions support 8. Tap the block list for a larger breakdown.

## Source and validation

The complete project is preserved in `Pimatech-Gage-Blocks-1.0.0-Source.zip`. Extract it, open `PimatechBlockResolver` in Android Studio, and follow the enclosed README. It includes Kotlin/Compose UI, the pure Kotlin solver, Gradle wrapper, tests, engineering notes, rendered screens and validation evidence. JDK 17 and Android SDK 35 are required.

Build, nine engine test groups (including 400 independent exhaustive-subset comparisons), four host-side UI tests, Android lint and APK signature checks passed. The owner reviewed and approved this version. Physical-device measurement acceptance is still the operator's responsibility.

Source is currently stored as a versioned archive. Private signing keys are excluded.

## Measurement limits

EXACT describes nominal arithmetic, not a certification of the realized stack. Calibration corrections, wringing film, temperature, wear, cleanliness and measurement uncertainty are not compensated. Verify the preset against your actual set; brands and compositions vary. The app does not infer an acceptable tolerance for an approximate stack.

## License

MIT License; see LICENSE. Third-party components retain their own licenses.

Proudly made and released open source by PimaTech.org.
