# OmegA engine

[![Build](https://github.com/OpenArena-Ioq3/openarena-ioq3/actions/workflows/build.yml/badge.svg)](https://github.com/OpenArena-Ioq3/openarena-ioq3/actions/workflows/build.yml)

![OmegA Logo](omega_logo.svg)

This is a fork of OpenArena-Ioq3 for use with OmegA. The goal is to provide players with an up-to-date engine designed for running OmegA.

# Compilation and installation

For *nix

  1. Change to the directory containing this readme.
  2. Run 'make'.

For Windows,
  
  1. Please refer to the excellent instructions here:
     https://ioquake3.org/help/building-ioquake3/

For macOS, building a Universal Binary (macOS 10.5 to 10.8, x86_64, x86, ppc)
  1. Install MacOSX SDK packages from XCode.  For maximum compatibility,
     install MacOSX10.5.sdk and MacOSX10.6.sdk.
  2. Change to the directory containing this README file.
  3. Run './make-macosx-ub.sh'
  4. Copy the resulting ioquake3.app in /build/release-darwin-universal
     to your /Applications/ioquake3 folder.

For macOS, building a Universal Binary 2 (macOS 10.9+, arm64, x86_64)
  1. Install MacOSX SDK packages from XCode.  Building for arm64 requires
     MacOSX11.sdk or later.
  2. Change to the directory containing this README file.
  3. Run './make-macosx-ub2.sh'
  4. Copy the resulting ioquake3.app in /build/release-darwin-universal2
     to your /Applications/ioquake3 folder.

Installation, for *nix

  1. Set the COPYDIR variable in the shell to be where you installed Quake 3
     to. By default it will be /usr/local/games/quake3 if you haven't set it.
     This is the path as used by the original Linux Q3 installer and subsequent
     point releases.
  2. Run 'make copyfiles'.

It is also possible to cross compile for Windows under *nix using MinGW. Your
distribution may have mingw32 packages available. On debian/Ubuntu, you need to
install 'mingw-w64'. Thereafter cross compiling is simply a case running
'PLATFORM=mingw32 ARCH=x86 make' in place of 'make'. ARCH may also be set to
x86_64.

The following variables may be set, either on the command line or in
Makefile.local:

```txt
  CFLAGS               - use this for custom CFLAGS
  V                    - set to show cc command line when building
  DEFAULT_BASEDIR      - extra path to search for baseq3 and such
  BUILD_SERVER         - build the 'ioq3ded' server binary
  BUILD_CLIENT         - build the 'ioquake3' client binary
  BUILD_BASEGAME       - build the 'baseq3' binaries
  BUILD_MISSIONPACK    - build the 'missionpack' binaries
  BUILD_GAME_SO        - build the game shared libraries
  BUILD_GAME_QVM       - build the game qvms
  BUILD_STANDALONE     - build binaries suited for stand-alone games
  SERVERBIN            - rename 'ioq3ded' server binary
  CLIENTBIN            - rename 'ioquake3' client binary
  USE_RENDERER_DLOPEN  - build and use the renderer in a library
  USE_YACC             - use yacc to update code/tools/lcc/lburg/gram.c
  BASEGAME             - rename 'baseq3'
  BASEGAME_CFLAGS      - custom CFLAGS for basegame
  MISSIONPACK          - rename 'missionpack'
  MISSIONPACK_CFLAGS   - custom CFLAGS for missionpack (default '-DMISSIONPACK')
  USE_OPENAL           - use OpenAL where available
  USE_OPENAL_DLOPEN    - link with OpenAL at runtime
  USE_CURL             - use libcurl for http/ftp download support
  USE_CURL_DLOPEN      - link with libcurl at runtime
  USE_CODEC_VORBIS     - enable Ogg Vorbis support
  USE_CODEC_OPUS       - enable Ogg Opus support
  USE_MUMBLE           - enable Mumble support
  USE_VOIP             - enable built-in VoIP support
  USE_FREETYPE         - enable FreeType support for rendering fonts
  USE_INTERNAL_LIBS    - build internal libraries instead of dynamically
                         linking against system libraries; this just sets
                         the default for USE_INTERNAL_ZLIB etc.
                         and USE_LOCAL_HEADERS
  USE_INTERNAL_ZLIB    - build and link against internal zlib
  USE_INTERNAL_JPEG    - build and link against internal JPEG library
  USE_INTERNAL_OGG     - build and link against internal ogg library
  USE_INTERNAL_OPUS    - build and link against internal opus/opusfile libraries
  USE_LOCAL_HEADERS    - use headers local to ioq3 instead of system ones
  DEBUG_CFLAGS         - C compiler flags to use for building debug version
  COPYDIR              - the target installation directory
  TEMPDIR              - specify user defined directory for temp files
```

The defaults for these variables differ depending on the target platform.

## Console

### New cvars

```txt
  cl_consoleHeight                  - change the console size
  cl_consoleType                    - make possible to switch between base and stock transparent console
  cl_consoleColorRed                - needs cl_consoleType 2, set the percentage of red in the console
  cl_consoleColorGreen              - needs cl_consoleType 2, set the percentage of green in the console
  cl_consoleColorBlue               - needs cl_consoleType 2, set the percentage of blue in the console
  cl_consoleColorAlpha              - needs cl_consoleType 2, set the percentage of transparency in the console
```

# Thank You

  * an_origamian
