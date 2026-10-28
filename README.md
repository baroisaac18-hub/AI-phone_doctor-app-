# AI Phone Doctor

**AI Phone Doctor** is an Android device diagnostics and maintenance assistant designed to help users inspect their phones, understand diagnostic results, and access practical device tools.

The app emphasizes transparency: diagnostic scans are intended to be read-only, and the interface reports information as unavailable when it cannot be measured. Actions that require shell access should only be performed with the user's permission.

> **Project status:** Update this section to reflect whether the project is experimental, in development, or ready for release.

## Features

### Device diagnostics
- Scan the phone and display available diagnostic information.
- Read-only diagnostic approach: diagnostics do not intentionally clean, boost, or terminate processes.
- Report unavailable measurements rather than presenting guesses as facts.

### AI Doctor
- Chat with an optional on-device language model.
- Use the assistant to interpret scan results and explain potential fixes.
- Shell access is presented separately and requires user authorization before privileged operations.

### Shell
- Run supported shell commands through ADB/Shizuku when the required permission is available.
- View command output in the app.
- Review the command log and refresh shell status.

**Security note:** ADB/Shizuku shell access can allow commands to affect device settings or data. Review each command before running it. Do not execute commands suggested by an AI assistant without understanding their effects.

### Tools
- **Network tools:** Ping, local-network scan, port checks, DNS tools, and download-speed checks.
- **Wallpaper:** Read the current wallpaper and set a new one.
- **Cleanup analysis:** Measure cache and temporary-file space without automatically deleting files.
- **APK installer:** Install an APK with package-manager options when the required Shizuku access is available.
- **Color tools:** Pick, mix, and inspect colors.

Availability depends on Android version, permissions, and device support.

## Optional on-device AI models

The app can work without a language model. Downloading a model enables local inference and may allow AI features to work offline, subject to the selected model and the app's implementation.

Models shown in the current interface:

| Model | Quantization | Approx. download size | Listed RAM requirement |
|---|---|---:|---:|
| SmolLM2 135M Instruct | Q8_0 (8-bit) | 138 MB | 2+ GB |
| Qwen2.5 0.5B Instruct | Q8_0 (8-bit) | 644 MB | 4+ GB |
| Qwen2.5 1.5B Instruct | Q8_0 (8-bit) | 1,807 MB | 6+ GB |

The interface lists Android 26+ for these models. Confirm the actual minimum Android version and model compatibility in the project configuration before publishing.

Model download sizes and memory needs are approximate. Actual performance depends on the phone, available RAM, context length, and inference implementation. Local execution does not automatically mean every app feature works offline.

## Requirements

Requirements depend on the build and enabled features. The current interface indicates:

- An Android device.
- Optional ADB/Shizuku setup for shell-based features.
- Internet access to download optional models and use network-dependent tools.
- Sufficient free storage and RAM for the selected model.

Some functions may be unavailable without the necessary permission, Android version, or hardware support.

## Permissions and privacy

AI Phone Doctor should request only the permissions needed for features the user chooses to use.

- On-device models are intended to run locally after download.
- Shell-based operations require the appropriate access path and user authorization.
- Network tools may send traffic to the selected network destinations.
- Installing APKs or changing the wallpaper can modify the device.
- Review the app's source code and Android permission declarations to verify its actual behavior.

Do not describe the app as fully private, fully offline, or risk-free unless that has been verified for the specific build and all enabled features.

## Safety principles

1. Keep diagnostic scans read-only.
2. Clearly distinguish measured results from estimates and unavailable data.
3. Ask for explicit user authorization before shell operations that change the device.
4. Explain potentially destructive commands before execution.
5. Never delete files, kill processes, or change settings as an automatic side effect of a diagnostic scan.

## Installation

Installation instructions depend on how the project is distributed.

### Install from a release APK
1. Open the project's **Releases** page on GitHub.
2. Download the APK for your device, if a release is available.
3. Verify the source and release notes before installing.
4. Allow installation from that source if Android requests it.

### Build from source
Source-build instructions have not been supplied in this README. Add the project's actual build steps here, including the required JDK, Android SDK, build command, and any model/runtime setup. Do not publish guessed commands.

## Usage

1. Open **AI Phone Doctor**.
2. Choose **Scan my phone** to start a diagnostic scan.
3. Open **Open tools** to access network, wallpaper, cleanup-analysis, APK-installer, and color utilities.
4. Open **Open AI doctor** to use the assistant.
5. Select and download an optional on-device model if local AI inference is supported by the installed build.
6. Use **Open shell** only when you understand the command and have configured the required access.

Names and behavior may differ between development builds.

## Known limitations

- Diagnostics can only report information that Android and the app's available permissions expose.
- AI-generated explanations can be incorrect; verify recommendations before applying them.
- Larger language models require more memory and storage and may run slowly on some phones.
- Some features depend on Shizuku/ADB and may not work on every device.
- The screenshots alone do not establish the app's minimum Android version, build process, license, or full permission behavior.

## Roadmap

Possible areas for future development:

- More device diagnostics with clear explanations of each measurement.
- Exportable diagnostic reports.
- Better handling of unsupported commands and unavailable permissions.
- Confirmation screens for potentially risky actions.
- Documented build and release instructions.

Edit this list to reflect the actual project roadmap.

## Contributing

Contributions are welcome if the repository owner enables them. Before submitting a pull request:

1. Describe the problem or proposed improvement.
2. Test the change on supported Android versions.
3. Explain any new permissions or shell commands.
4. Include screenshots or logs when useful, with personal information removed.

## License

**License not specified yet.** Add a `LICENSE` file and replace this section with the chosen license before distributing the project. Do not assume that the model licenses also determine the license for the application code.

## Disclaimer

AI Phone Doctor is a device utility, not a guarantee of device health or security. Diagnostic output and AI recommendations may be incomplete or inaccurate. The user is responsible for reviewing and authorizing changes made to their device.
