# Changelog

All notable changes, improvements, and fixes for official Agneax OS releases are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [v0.1.0] - 2026-10-26

### Added
- Initial public ISO release of Agneax OS.
- Complete **Agneax Desktop** shell with top status bar, notification center, control center, and dynamic bottom dock.
- Integrated **Agneax UI** design system supporting seamless Light and Dark mode transitions.
- Native application suite:
  - **Agneax File Manager**: Tabbed folder browsing, archive compression/extraction, and quick sidebar navigation.
  - **Agneax Terminal**: Hardware-accelerated terminal emulator with custom color themes and split layouts.
  - **Agneax System Settings**: Centralized control panel for display scaling, networking, audio, and personal appearance.
  - **Agneax System Updater**: Graphical package and system upgrade utility.
  - **Agneax Package Installer**: One-click installation and verification tool for standalone application packages.
  - **Agneax Multimedia Suite**: Native Image Viewer, Video Player, and Camera capture tools.
- Dedicated background **Application Engine** for instant cold app launches and optimized process life cycles.
- Graphical system installer supporting UEFI and Legacy BIOS boot architectures.

### Security
- Hardened default kernel parameters and long-term security maintenance base.
- Clean separation of standard user privileges with administrative elevation prompts.
