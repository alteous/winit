# Unreleased

- Uniformize keyboard scancode values accross Wayland and X11 (#297).

# Version 0.8.1 (2017-09-22)

- Added various methods to `os::linux::EventsLoopExt`, plus some hidden items necessary to make
  glutin work.

# Version 0.8.0 (2017-09-21)

- Added `Window::set_maximized`, `WindowAttributes::maximized` and `WindowBuilder::with_maximized`.
- Added `Window::set_fullscreen`.
- Changed `with_fullscreen` to take a `Option<MonitorId>` instead of a `MonitorId`.
- Removed `MonitorId::get_native_identifer()` in favor of platform-specific traits in the `os`
  module.
- Changed `get_available_monitors()` and `get_primary_monitor()` to be methods of `EventsLoop`
  instead of stand-alone methods.
- Changed `EventsLoop` to be tied to a specific X11 or Wayland connection.
- Added a `os::linux::EventsLoopExt` trait that makes it possible to configure the connection.
- Fixed the emscripten code, which now compiles.
- Changed the X11 fullscreen code to use `xrandr` instead of `xxf86vm`.
- Fixed the Wayland backend to produce `Refresh` event after window creation.
- Changed the `Suspended` event to be outside of `WindowEvent`.
- Fixed the X11 backend sometimes reporting the wrong virtual key (#273).
