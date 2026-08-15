
## v0.1.0 - 2026-08-15

### Bug Fixes

* stabilize Hyprland 0.55 plugin integration
* working with shadow enable, not yet with shadow disabled
* don't dim glass by inactive alpha and opacity rules
* use MONITORID instead of Monitor::CMonitor, unavailable before hyprland 0.56 ([#44](https://github.com/Hyprnux/hyprglass/issues/44))
* relax version check to compare ABI suffix only
* qualify CMonitor with Monitor:: namespace
* wrong viewport restore after blur on transformed monitors ([#41](https://github.com/Hyprnux/hyprglass/issues/41))
* match dynamic window tags for preset selection ([#45](https://github.com/Hyprnux/hyprglass/issues/45))
* keep layer mask threshold stable during fade
* initialize presets before validation
* support legacy string config values
* clean up decoration lifetime on unload
* set noblur on glassed windows, glass replaces hyprland blur ([#46](https://github.com/Hyprnux/hyprglass/issues/46))
* use source framebuffer format for layer temp FBO in HDR mode
* fading workspace  animations were not fading the glass layer ([#24](https://github.com/Hyprnux/hyprglass/issues/24))
* correct redraw artifact on multi-monitor setup
* some low opacity layers on XRGB monitors where shown without the effect
* preset configuration was not correctly picked up ([#11](https://github.com/Hyprnux/hyprglass/issues/11))
* need to always resample to catch real time background change, cheap GPU overhead, but no way to do otherwise as of now
* refactor shader creation for 0.54 refactored shader logic
* refactor callbacks for new event bus listeners
* when workspace animation occurs and no windows were on workspace, effect was not redrawn (useful when background animation occur on workspace changes)
* area was not damaged correctly  when moving while tiled layout
* remove some optimization causing noise when rendering blur and moving window (not worth it)
* gpu infinite render
* border radius
* **ci:** build tag from hyprland version bump was not picked up for release

### Build System

* include Lua 5.4 headers
* update hyprland compatibility to v0.56.0
* update hyprland compatibility to v0.55.4
* update hyprland compatibility to v0.55.3
* update hyprland compatibility to v0.55.2
* update hyprland compatibility to v0.54.3
* improved the makefile to allow for parallel builds + fix linker flag
* update hyprland compatibility to v0.54.2
* update hyprland compatibility to v0.54.1
* update hyprland compatibility to v0.54.0
* update hyprland compatibility to v0.53.3

### CI/CD

* pipelines + docs
* **hyprpm:** correctly pin to hyprland versions ([#38](https://github.com/Hyprnux/hyprglass/issues/38))

### Chores

* add BSD 3-Clause license
* remove some standard uniform names (already resolved internally by CShader since Hyprland 0.54)
* **release:** v0.3.0 [skip ci]
* **release:** v0.2.7 [skip ci]
* **release:** v0.6.1 [skip ci]
* **release:** v0.6.0 [skip ci]
* **release:** v0.5.0 [skip ci]
* **release:** v0.4.1 [skip ci]
* **release:** v0.4.0 [skip ci]
* **release:** v0.3.1 [skip ci]
* **release:** v0.7.0 [skip ci]
* **release:** v0.6.2 [skip ci]
* **release:** v0.2.6 [skip ci]
* **release:** v0.2.5 [skip ci]
* **release:** v0.2.4 [skip ci]
* **release:** v0.2.3 [skip ci]
* **release:** v0.6.3 [skip ci]
* **release:** v0.6.4 [skip ci]
* **release:** v0.2.2 [skip ci]
* **release:** v0.2.1 [skip ci]
* **release:** v0.2.0 [skip ci]
* **release:** v0.1.0 [skip ci]

### Code Refactoring

* better file separation, renaming
* remove unused code and fix bounding box
* attempt with glass shader using SDF bezel refraction and poisson blur

### Documentation

* add troubleshooting section
* add Lua config example
* **configuration:** reorganize docs + enhance lua/conf doc ([#16](https://github.com/Hyprnux/hyprglass/issues/16))

### Features

* add color_tint effect
* settings improvments, with presets and built-in presets
* draft working version of shader for transparent windows
* add ability to enable/disable hyprglass effect per-window ([#23](https://github.com/Hyprnux/hyprglass/issues/23))
* almost perfect
* handle layer decoration - BETA ([#6](https://github.com/Hyprnux/hyprglass/issues/6))
* add HYPRGLASS_SKIP_VERSION_CHECK escape hatch ([#44](https://github.com/Hyprnux/hyprglass/issues/44))
* improve settings
* add UV padding and remove wave distorsion
* more like apple variant, magnifying variant, seemd to be more beautiful
* add meniscus dispersion, color, and border rim to glasss shader (attempt to make it more apple-like, cool effects but not a big usable success)"
* tweaking little bit different approach
* compatibility hyprland 0.56
* split corner/bezel SDF, add multi-pass blur and inner shadow (in order to avoid weird corners, but not really a success yet)
* **configuration:** improve lua configuration using lua functions ([#16](https://github.com/Hyprnux/hyprglass/issues/16))
* **layers:** add namespace_mask_thresholds for better shadow handling + fix some config parsing issues

### Performance Improvements

* conditionaly make half-res blur if blur_strenght is sufficient enough
* reduce GPU overhead for layer glass effect, still not perfect ([#6](https://github.com/Hyprnux/hyprglass/issues/6))
* massive gpu usage improvments, resample only when really needed
* shared blur framebuffers, remove raw texture sampler
* half-res blur pipeline, linear sampling, shadows

