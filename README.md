# AIOForge

**AIOForge (AIOF)** is a lightweight Windows audio management tool focused on granular control of audio devices, application audio, and configurable automation.

It brings device management, per-application audio controls, profiles, DSP processing, and command-based hotkeys together in one compact application.

🌐 **Website:** https://aiof.patched.cc  
📦 **Downloads:** https://github.com/sirpatch/AIOForge/releases/  
⚙️ **PLUGIN SDK / KIT** https://github.com/sirpatch/AIOForge/releases/download/V0.34.2/AIOF-PluginSDK-1.1.0.zip

**Download only AIOF_VX.XX.X.xip** There is no usage for *.txt* and *txt.sig* files on client-side.

> AIOForge is actively developed. Some hardware-related functionality remains experimental and behavior can vary depending on the audio device, codec, driver, and Windows configuration.

---

## Features

### Audio device management

<img width="1980" alt="out" src="https://github.com/user-attachments/assets/5e040620-18bc-4efc-9090-b740fc3254f3"/>
<img width="1920" alt="cfg" src="https://github.com/user-attachments/assets/09a3156b-c775-4e6b-a00e-c78ea23149b8" />

- Monitor available audio input and output devices.
- Change the default playback and recording devices.
- Control device volume and mute state.
- Enable or disable individual devices.
- Configure microphone mute state and volume.
- Configure audio enhancements and exclusive-mode settings.
- Change supported audio formats, including sample rate and bit depth.
- Configure speaker layout and channel levels where supported.

### Per-application audio control

<img width="1980" alt="apps" src="https://github.com/user-attachments/assets/be8b42fb-a37a-4572-bfc2-c6992a2b71a3" />

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

---

## DSP Engine

<img width="1980" alt="dsp" src="https://github.com/user-attachments/assets/89592506-355e-444e-a1a1-01688bcfdbd4" />

Introduced in **AIOForge V0.34.0**, the integrated DSP engine brings digital signal processing capabilities to individual applications and audio output devices.

Each DSP insert equalizes **one application or one output device**.

### Equalizer

AIOForge features a configurable multi-band equalizer supporting up to **32 frequency bands**.

Features include:

- Application-level EQ.
- Device-level EQ.
- Custom user-created presets.
- Preset creation and management.
- Add and remove individual frequency bands.
- Enable or disable individual bands.
- Built-in presets.
- Save, rename, delete, import, and export presets.

**Equalizer parameters:**

| Parameter | Range / Options | NOTICES |
|---|---|---|
| Frequency | 20 Hz – 20 kHz | Only GUI limits |
| Gain | -18 dB to +18 dB | Only GUI limits |
| Filter Type | Configurable | - |
| Q Factor | Configurable | - |

**Advanced parameter editing**

EQ band parameters can be entered manually using numeric input fields.

This allows users to enter precise custom values beyond the increments or ranges exposed by the GUI sliders and controls.

### Additional DSP Controls

The DSP engine provides several additional processing controls.

**General**

- Preamp
- Balance
- Stereo width
- Channel configuration

**Limiter**

- Enable or disable limiter.
- Adjustable ceiling.
- Adjustable release time.

**Compressor**

- Enable or disable compressor.
- Adjustable threshold.
- Adjustable ratio.
- Adjustable attack time.
- Adjustable release time.
- Adjustable makeup gain.

### Multichannel Audio

DSP supports more than standard stereo output, with multichannel configurations supported up to **7.1 surround sound**.

Channel configuration can be selected directly in the DSP editor.

### Processing Order

The DSP processing chain follows this order:

1. Channels
2. Width
3. Preamp
4. EQ bands
5. Compressor
6. Balance
7. Limiter

An A/B bypass control is also available for comparing processed and bypassed audio during live preview.

### DSP Routing

AIOForge supports flexible DSP routing, allowing users to choose between direct playback and separate-output configurations.

**DIRECT mode**

- Process audio using a single output device.
- No separate destination output is required.
- Enable the `DIRECT` checkbox to use this configuration.

**Two-output mode**

- Use a separate source and destination output configuration.
- Disable `DIRECT` to use the separate-output routing configuration.
- Useful for setups involving multiple audio devices.

### DSP SHARE AUDIO

Introduced in AIOForge V0.34.2

supports playing one audio stream across many decices at once.

WARNING: audio quality may be lower and/or vary between devices.

### Hotkey Integration

DSP presets integrate with AIOForge's command-based hotkey system.

Users can:

- Apply DSP presets using hotkeys.
- Change DSP configurations through automated command sequences.
- Include DSP preset changes in broader audio-control workflows.

This allows audio-processing configurations to become part of automated workflows alongside AIOForge's existing application, device, output, and profile management.

### Future Development

The DSP engine is under active development. Additional filters, effects, and audio-processing capabilities are planned for future updates.

---

### Plugins

<img width="1980" alt="mods" src="https://github.com/user-attachments/assets/68a704d7-96ad-4adf-99be-1159ab70f906" />

AIOForge supports a plugin system with a Plugin SDK. The latest release includes an update to the SDK and compatibility fixes for launching the application with the latest plugin SDK.

See the [project website](https://aiof.patched.cc) for plugin and module information.

---

## Experimental functionality

### Jack retasking

Jack detection and retasking are experimental and hardware-dependent. Detection may be inconsistent, and changing a jack's function is not reliable across codecs and drivers. Treat this functionality as experimental rather than a generally supported feature.

---

## Resource usage

The following figures are **user-observed measurements**, not official benchmarks. Actual usage can vary depending on the system, audio devices, drivers, and workload.

| Metric | Observed usage | NOTICES |
|---|---|---|
| Application size | Less than 2 MB | 1139858 bytes |
| CPU idle | 0–0.4% | - |
| CPU peak | ~4% | - |
| RAM idle | 2–55 MB | Depends on GC and tool usage |
| RAM peak | ~55 MB | - |

<sub>Measurements reported on AIOForge V0.34.1 They should be treated as examples, not performance guarantees for every version or system.</sub>

---

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
