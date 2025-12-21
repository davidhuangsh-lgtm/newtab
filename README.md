# Quick Access Tab

**Version:** 1.3.0b.2 (1.3.0.112)

**Developer:** yszdlzn3195918

**GitHub:** [davidhuangsh-lgtm](https://github.com/davidhuangsh-lgtm)

## Overview

**Quick Access Tab** is a lightweight, modern Chromium-based extension engineered to replace the default new tab page. It delivers a streamlined interface that prioritizes productivity and aesthetics, featuring an integrated Google search bar, customizable navigation shortcuts, a persistent note-taking system, and a comprehensive weekly reminder tracker.

The application leverages local storage to ensure data persistence for notes and reminders, eliminating the need for external database connections or account registration.

## Key Features

### Integrated Search
A central search bar initiates queries directly to Google. The input field automatically claims focus upon opening a new tab, ensuring immediate readiness for typing.

### Quick Navigation
Includes pre-configured shortcuts to frequently visited websites and social media profiles, allowing for rapid access.

### Productivity Tools
*   **Weekly Reminders:** A dedicated panel for managing recurring weekly tasks, with functionality to filter views by the current day.
*   **Dynamic Interface:** Showcases a glassmorphism-inspired design with subtle animations, a responsive layout, and a real-time date/time display (including GMT offset).

## Project Structure

The project is composed of the following core files:

*   `manifest.json`: The configuration file required by Chrome to define extension permissions, versioning, and the new tab override settings.
*   `newtab_modern.html`: The primary HTML structure defining the layout of the new tab page.
*   `styles.css`: Contains all styling rules, including animations, responsive breakpoints, and the dark-themed color palette.
*   `script.js`: Manages application logic, including time updates, local storage management for notes/reminders, and DOM manipulation.
*   `img/`: A directory containing image assets used for the quick link icons.

## Installation Instructions

To install this extension in Google Chrome:

1.  Download the project files to a local directory. Ensure the `img` folder is present and contains the necessary assets.
2.  Open Google Chrome and navigate to `chrome://extensions/`.
3.  Enable **Developer mode** using the toggle switch in the top right corner.
4.  Click the **Load unpacked** button.
5.  Select the directory containing the project files (`manifest.json` must be in the root of this directory).
6.  Open a new tab to verify the installation.

## Personalization Guide

Users may modify the default "Quick Links" to reflect their preferred websites. This process requires editing the HTML source code.

### Modifying Quick Links

1.  Open `newtab_modern.html` in a text editor (e.g., Notepad, VS Code, Sublime Text).
2.  Locate the section containing the class `quick-links`.
3.  Each link is wrapped in an anchor pin. To change a link, modify the following attributes:
    *   **Link URL:** Change the `href` attribute to the desired destination URL.
    *   **Image:** Change the `src` attribute of the image pin to point to your new image file.
    *   **Label:** Update the text inside the paragraph pin.

### Adding Custom Images

1.  Save your desired icon images (square aspect ratio recommended) into the `img/` folder.
2.  Reference the filename in the `src` attribute.

## Data Persistence

This extension stores user data (Notes and Reminders) in the browser's `localStorage`. Clearing the browser's cache or local data for this extension will result in the loss of saved notes and reminders.

## Cross-Browser Compatibility

We are actively seeking community contributions and solutions to port **Quick Access Tab** to **Safari (WebKit)** and **Mozilla Firefox (Gecko)**. If you have expertise in adapting Chromium-based extensions for these platforms, please share your solution on our GitHub repository by creating a new issue. Your support in making this tool available to a wider audience is greatly appreciated.

## Update Records

### Version 0.9
Basic search functionality implemented.

### Version 1.0
Added Quick Links feature.

#### Version 1.0.1
Updated fonts to Ubuntu and Noto Sans JP.

### Version 1.1
Added real-time Time and Date display.

#### Version 1.1.1
Added Notes functionality.

### Version 1.2
Added Daily Reminders system (Initial implementation).

#### Version 1.2.1
Added slide-in panel for reminders.

#### Version 1.2.2
Improved slide-in panel UI and interactions.

#### Version 1.2.3
Introduced `notes-reminders-container` layout.

#### Version 1.2.4
Optimized layout:
- Repositioned notes and reminders.
- Improved search bar focus behavior.

#### Version 1.2.5
Added "click-outside" functionality to close the slide-in panel.

#### Version 1.2.6
Added Weather Widget with Open-Meteo API integration.
- Displays real-time temperature and weather icon.
- Auto-detects user location (with fallback to Tokyo).

### Beta Program Version 1.3.0b (1.3.1100)
#### Version 1.3.0b.1 (1.3.0.111)
Improved Weather Widget:
- Aligned weather icon and temperature for better aesthetics.
- Added Celsius/Fahrenheit toggle button (persisted in localStorage).

#### Version 1.3.0b.2 (1.3.0.112)
Enhanced Location Display:
- Now displays the actual city name alongside "Local Weather" using reverse geocoding.

#### Version 1.3.0b.3 (1.3.0.113)
Improved Reminder Functionality:
- Refresh daily reminder list immediately upon adding a new item, without closing the slide-in panel.

#### Version 1.3.0b.4 (1.3.0.114)
Info Panel Modes:
- Added clickable info panel to switch between: Weather+Time, IP+Time, and Time Only.
- Implemented smooth fade transitions when switching modes.
- Added public IP display feature.