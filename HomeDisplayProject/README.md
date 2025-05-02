# Touchscreen Dashboard Project

##  Project Goal

Build a self-hosted, portrait-oriented touchscreen dashboard using a Dell AIO running Ubuntu 24.04. The dashboard will:

* Display full-screen, swipeable panes (Grocy, Calendar, Whiteboard, Weather, Cooking Mode)
* Host Grocy and other tools locally
* Use a physical USB button to exit kiosk mode
* Sleep overnight and wake in the morning

---

## Completed Steps

### System Setup

* Installed Ubuntu 24.04 Desktop (full version)
* Confirmed touchscreen and display functionality
* Upgraded RAM to 16GB and installed 500GB SSD

### Hardware Design

* Confirmed power draw is acceptable (\~30W idle)
* Decided on no system monitoring in Phase 1
* Physical 2-button USB controller planned for admin escape

### Shared Calendar Setup

* Created Google Family Calendar

---

---

## In Progress

### Web Server Setup (local hosting)

* Install Nginx, PHP, PHP-FPM, SQLite
* Set up Grocy under `http://localhost/grocy`

###  Kiosk Interface

* Create fullscreen Chromium startup script
* Confirm portrait orientation with xrandr
* Add swipeable HTML dashboard (5 panes)

  * Grocy
  * Embedded Google Calendar (shared family calendar)
  * Whiteboard (Etherpad or similar)
  * Weather (static iframe or widget)
  * Cooking Mode (YouTube, auto-rotate to landscape)

### Usability

* Install on-screen keyboard (Onboard)
* Ensure keyboard appears when tapping fields in Chromium
* Lock down desktop session (auto-login, no taskbar, etc.)

---

## Directory Plan

* `/var/www/grocy` — Grocy files
* `/var/www/dashboard` — swipeable interface
* `/var/www/launcher` — optional admin launcher or button interface

---

## Notes

* Voice control not needed (future fun project)
* Cooking Mode can be rotated into via swipe gesture, iframe loads YouTube
* Dashboard should feel like an appliance — no visible desktop
