# AIOForge

**AIOForge (AIOF)** is a lightweight Windows audio management tool focused on granular control of audio devices, application audio, and configurable automation.

It brings device management, per-application audio controls, profiles, and command-based hotkeys together in one compact application.

🌐 **Website:** https://aiof.patched.cc  
📦 **Downloads:** https://github.com/sirpatch/AIOForge/releases/

> AIOForge is actively developed. Some hardware-related functionality remains experimental and behavior can vary depending on the audio device, codec, driver, and Windows configuration.

---

## Features

### Audio device management

- Monitor available audio input and output devices.
- Change the default playback and recording devices.
- Control device volume and mute state.
- Enable or disable individual devices.
- Configure microphone mute state and volume.
- Configure audio enhancements and exclusive-mode settings.
- Change supported audio formats, including sample rate and bit depth.
- Configure speaker layout and channel levels where supported.

### Per-application audio control

- Detect and track application audio sessions.
- Adjust or mute individual applications.
- Route an application's audio to another output device.
- Send an application to the next available output or a selected output.

### Command-based hotkeys

Each hotkey can execute an ordered list of commands, rather than being limited to a single action. This makes it possible to build multi-step audio workflows and trigger them with one keyboard shortcut.

Available command groups include:

- **Output:** change the default output, switch to the next or previous output, and control output volume or mute state.
- **Input:** change the default input and control microphone volume or mute state.
- **Device:** control a specific device's volume, mute state, enabled state, audio enhancements, exclusive-mode setting, format, and speaker layout.
- **App:** mute or adjust an application's volume and route it to another output.
- **Profile:** apply a profile or move to the next or previous profile.
- **System:** show or hide the main window, open the quick mixer, and wait before continuing a command sequence.
- **Run:** launch a program or open a link.

### Profiles

AIOForge supports applying and cycling through audio profiles. Profiles can also be invoked from command-based hotkeys.

### Device and driver information

AIOForge exposes technical information about the audio stack, including:

- Audio codec information.
- Driver information.
- Audio API stack identification.
- Registry path information.
- Kernel Streaming (KS) device enumeration.

## DSP Engine

AIOForge V0.34.0 introduces an integrated DSP engine with support for both application-level and audio-device-level equalization.

### Equalizer and Presets

- Application EQ and device EQ.
- Create, edit, and manage custom user presets.
- Frequency range: 20 Hz – 20 kHz.
- Gain range: -18 dB to +18 dB.
- Configurable filter parameters:
  - Type
  - Frequency
  - Gain
  - Q factor
- Additional controls:
  - Limiter
  - Compressor
  - Preamp
  - Balance
  - Width
  - Channel configuration

DSP presets can be changed and applied through AIOForge's command-based hotkey system, allowing audio-processing configurations to become part of automated workflows.

### Plugins

AIOForge supports a plugin system with a Plugin SDK. The latest release includes an update to the SDK and compatibility fixes for launching the application with the latest plugin SDK.

See the [project website](https://aiof.patched.cc) for the plugin and module information.

---

## Experimental functionality

### Jack retasking

Jack detection and retasking are experimental and hardware-dependent. Detection may be inconsistent, and changing a jack's function is not reliable across codecs and drivers. Treat this functionality as experimental rather than a generally supported feature.

---

## Resource usage

The following figures are **user-observed measurements**, not official benchmarks. Actual usage can vary depending on the system, audio devices, drivers, and workload.

| Metric | Observed usage |
|---|---:|
| SPACE NEEDED | LESS THAN 5 MB |
| CPU idle | 0–0.4 % |
| CPU peak | ~3.9 % |
| RAM IDLE | 2-35 MB |
| RAM PEAK| ~35 MB |

<sub>Measurements reported on AIOForge V0.33.4 They should be treated as an example, not a performance guarantee for every version or system.</sub>

## Planned / not currently available

The following items should not be considered working features unless a future release explicitly announces them:

- Optional per-input EQ.
- Media playback controls such as play, pause, next, and previous.

---

## Configuration and updates

- Application configuration files are stored in the `cfg` directory under the AIOForge root directory.
- AIOForge includes an automatic updater. See the [GitHub releases page](https://github.com/sirpatch/AIOForge/releases/) for release-specific changes.

---

## Compatibility notes

Audio functionality depends on the capabilities and behavior of the installed Windows audio devices and drivers. Individual features may not be available on every system, and hardware-specific features such as jack retasking can behave differently between codecs.

For the latest changes, consult the [release notes](https://github.com/sirpatch/AIOForge/releases/).

---

## Tested audio hardware with RETASKING options

The following hardware was listed in earlier project testing notes:

| Codec | Reported status |
|---|---|
| Realtek ALC897 | Working |
| Conexant CX20590 | May lack retask support |

These results are not a guarantee of identical behavior on every system using the same codec; driver versions and system configuration can affect compatibility.
