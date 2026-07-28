# qs-minimal

> A minimal, performance-first Quickshell configuration for **Sway**.

`qs-minimal` is an attempt to answer a simple question:

> **How small can a modern Linux shell be while still providing everything you actually need?**

Most Quickshell configurations eventually become desktop environments of their own. They include dashboards, weather widgets, music controls, animations, graphs, theming systems, plugin frameworks, and hundreds of configuration options.

This project intentionally goes in the opposite direction.

Its purpose is to provide a **small, readable, fast, and extensible shell** that does one job well: replace the default desktop components without getting in your way.

---

# Project Goals

The goals of this project are intentionally strict.

Every feature, every dependency, and every line of code should contribute directly to one or more of these goals.

## 1. Performance Above Everything

Performance is the primary design constraint.

This project should:

* start as quickly as possible
* use as little memory as reasonably possible
* avoid unnecessary timers
* avoid polling whenever event-driven alternatives exist
* minimize QML object creation
* minimize startup allocations
* keep CPU usage effectively zero while idle

Features that negatively impact performance must justify their existence.

---

## 2. Minimalism

Minimal does **not** mean featureless.

Minimal means:

* every component has a purpose
* every file has a reason to exist
* every dependency solves an actual problem
* no duplicate abstractions
* no unnecessary complexity

If something can be removed without reducing usability, it should probably be removed.

---

## 3. Readability

The project should be understandable by someone who has never used Quickshell before.

Whenever possible:

* short files are preferred
* obvious code is preferred
* explicit code is preferred
* simple architecture is preferred

Clever code is discouraged.

This project should be approachable.

---

## 4. Maintainability

The shell should remain easy to modify years from now.

Avoid:

* deep inheritance
* giant utility libraries
* framework-like abstractions
* unnecessary indirection

Each module should be understandable in isolation.

---

## 5. Standalone

`qs-minimal` should not depend on another shell.

It is **not** a theme.

It is **not** a customization layer.

It is **not** a collection of patches.

It is its own project.

---

## 6. Sway First

This shell is built specifically for **Sway**.

It is **not** designed around Hyprland.

All integrations should use Sway's IPC wherever possible.

If support for other compositors is added in the future, it should never complicate the Sway implementation.

---

## 7. Black and White

The default appearance intentionally avoids trends.

No gradients.

No blur.

No transparency effects.

No glassmorphism.

No Material Design.

No Catppuccin.

No RGB.

No animated wallpapers.

The default interface consists of:

* black background
* white foreground
* simple borders
* clean typography

Users are free to theme the shell however they want, but the repository itself should remain visually neutral.

---

# Philosophy

This project follows a few simple principles.

## Every feature earns its place.

Nothing exists "just because."

Features are added only if they improve the shell while respecting the project's goals.

---

## Simplicity scales.

Small software is easier to:

* debug
* understand
* extend
* optimize
* rewrite

Complexity is treated as technical debt.

---

## Dependencies are expensive.

Every dependency increases maintenance costs.

New dependencies should only be introduced when they provide significant value.

---

## Configuration should be simple.

The default configuration should already be usable.

Most users should only need to modify a few values.

Avoid enormous configuration files.

---

## Extensibility matters.

Although the default shell is intentionally small, it should be easy to extend.

Users should be able to add modules without rewriting the existing architecture.

The core should remain stable.

---

# Planned Features

The initial release focuses only on essential desktop functionality.

## Top Bar

* Workspace indicator
* Running applications
* WiFi status
* System tray
* Clock
* Notification indicator
* Launcher button

Nothing else.

---

## Native Application Launcher

A lightweight launcher written entirely with Quickshell.

Goals:

* instant startup
* fuzzy search
* keyboard navigation
* application icons
* no external launcher required

The launcher replaces Wofi by default.

---

## Notifications

* popup notifications
* notification history
* notification dismissal
* minimal visual design

No excessive animations.

---

## Taskbar

The taskbar displays currently running applications.

It should:

* update instantly
* reflect Sway state
* allow focusing windows
* remain visually compact

---

## Workspaces

Simple workspace indicators.

No animations.

No decorative elements.

Only the information that matters.

---

# Non-Goals

This project intentionally does **not** aim to become a complete desktop environment.

The following are outside the scope of the core project:

* weather widgets
* music dashboards
* resource graphs
* desktop widgets
* wallpaper managers
* application launch effects
* animated workspace indicators
* highly configurable theme engines
* plugin ecosystems
* RGB effects
* blur-heavy interfaces

These can always exist as optional extensions.

They do not belong in the core.

---

# Code Style

Contributors are encouraged to follow these guidelines:

* Prefer clarity over cleverness.
* Prefer composition over abstraction.
* Keep files small.
* Avoid premature optimization.
* Avoid unnecessary helper functions.
* Delete unused code.
* Delete dead code instead of commenting it out.
* Keep modules independent whenever practical.

---

# Long-Term Vision

The long-term goal is to create one of the smallest fully usable Quickshell shells available.

The project should feel closer to software such as `dmenu`, `slock`, or `dwm` than to a traditional desktop environment.

It should provide the essentials, stay out of the user's way, and remain a solid foundation for people who want to build their own desktop experience without starting from scratch.
