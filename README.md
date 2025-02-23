# Firefox: Expand Vertical Tabs on Hover

This code enables vertical tabs in Firefox to automatically expand when hovering over them, displaying full tab titles with a smooth animation. This is a fork of [ENDE25/FIREFOX-tabs-hover-expand](https://github.com/ENDE25/FIREFOX-tabs-hover-expand).

## Features

- Narrow tabs sidebar with icons only by default
- Full tabs with title and close button on hover
- Smooth animation when expanding tabs
- Support for pinned tabs
- Faster animation times than the original version
- Slightly wider expanded width than the original version

![Demo](/demo.webp)


## 🛠️ Installation

>*To make this modification work, a small configuration in the browser is required, as described below:*

To apply this style in Firefox, follow these steps:

### 1️⃣ Enable `userChrome.css` Support
1. Open Firefox and type in the address bar: `about:config`
1. Accept the warning message if it appears.
1. Search for the preference: `toolkit.legacyUserProfileCustomizations.stylesheets`
1. Double-click it to set its value to `true`.

### 2️⃣ Find the User Profile Folder
1. Type in the address bar: `about:support`
1. Look for the **Profile Folder** section and click **Open Folder**.
1. Inside the profile folder, locate (or create if it doesn't exist) a folder named `chrome`, and inside it, another folder named `css`.

### 3️⃣ Apply the Style
1. Copy `css/expand-vertical-tabs-on-hover.css` from this repository into the `css` folder.
1. Copy the `userChrome.css` file into the `chrome` folder. If it already exists, append the content of this file to the existing one.
1. Restart Firefox for the changes to take effect.

That's it! Now your vertical tabs will automatically expand when hovered over. 🚀

## Known Issues

- The button to expand/collapse the sidebar will no longer work. This is because if this customization would respect it, tabs would remain expanded when the mouse leaves the sidebar, which is not the desired behavior. This would happen because FireFox automatically adds the `expanded` attribute when the button is clicked **and** when the mouse is over the sidebar. This prevents the CSS from distinguishing between the two cases, so instead it simply ignores the `expanded` attribute and only reacts to `:hover`.