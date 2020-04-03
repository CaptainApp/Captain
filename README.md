<img src="https://raw.githubusercontent.com/CaptainApp/Captain.Application/master/Resources/Logo.png" alt="Captain logo" />

![version: 0.6](https://img.shields.io/badge/version-0.6-blue.svg)
> The minimal, extensible screen capturer.

🚧 **Disclaimer: this is an ongoing project under active development, and is not yet meant to be usable.** 🚧

## What's this?
**TL;DR: Captain is an extensible screen capturing app that Just Works™ (on Windows).**

It's meant to take screenshots and record the screen. These captures may be saved to a file or uploaded to the
internet, or actually just about anything as long as there is an extension for that (and if there's not then go
ahead and roll your own!)

The whole thing is built with extensibility and flexibility in mind. That means it doesn't matter whether you
want to record WebM, HEVC or GIF videos or upload them to Imgur, your favourite pomf clone or whatever.

It also
means we'll capture the screen appropriately no matter what thing's on it (i.e.: **full-screen games**)

## Building from source
### Environment Requirements
- Windows 7 SP1 or newer (build only tested on latest Windows 10)
- [Visual Studio 2017](https://www.visualstudio.com/downloads/) or newer (Community edition is fine)  
  VS 2015 will most likely **not** work.

### Cloning
The project is split in git submodules, so don't forget the `--recursive` flag when cloning.

```
$ git clone --recursive https://github.com/CaptainApp/Captain
$ cd Captain
```

### Building
Then you can either open `Captain.sln` on Visual Studio or build it from the command-line:
```
$ nuget restore
$ devenv Captain.sln /Build
```

## Extending Captain
You can build extensions by inheriting from common classes on the `Captain.Common` namespace.

Refer to the [Captain.Common](https://github.com/CaptainApp/Captain.Common) source tree for more on this.
There will be documentation, eventually.

## Licensing
This software is made up of different components that may not necessarily be licensed under the same terms.
Refer to the `LICENSE.md` file in the top-level directory of each project to find further details about their
licensing.

Major components are licensed under the [simplified BSD license](https://opensource.org/licenses/BSD-2-Clause)
(a.k.a. BSD 2-Clause), with other smaller parts released [into the public domain](http://unlicense.org/).

## What's done?
_(Note that most unchecked features are still work in progress, but have already been started.)_

- [X] Still image capture
- [X] Video capture
  - [ ] Audio recording
- [ ] UI
  - [X] About dialog
  - [ ] Options
    - [X] General
    - [X] Workflows
    - [ ] Capture
    - [ ] Advanced
  - [ ] Post-capture graphics tooling
  - [X] HUD
- [ ] Extensibility
  - [ ] Stable API
  - [ ] Documentation
  - [ ] Compatibility with ShareX Custom Uploaders
- [ ] Installer/updater logic
- [ ] Screen capture foundations
  - [X] GDI
  - [X] DXGI desktop duplication on Windows 8 and upwards
  - [X] Direct3D 9 on Windows 7 (requires rework)
  - [ ] DWM SharedSurface's
  - [ ] DirectX hooks on DXGI < 1.5 for full-screen games
- [ ] Post-capture
  - [ ] Filters
  - [X] Handlers