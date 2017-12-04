# Compact dark-brown Firefox style for Tree Style Tab by Piro.

With the update to Firefox Quantum, I was no longer able to use Tab Tree by Sergey Zelentsov.
Looking for a replacement, I found that Tree Style Tab by Piro (which I used before Tab Tree) was working in Firefox Quantum.
By default, with that extension, the tabs are very large and too bright.
It takes 4 steps to get the proper vertical tabs experience.
1. Enable Firefox dark theme.
*Tools->Addons->Themes*. Press enable for the "Dark" theme.
2. Disable the horizontal tabs and the Sidebar Header (large field above your vertical tabs).
You disable the horizontal tabs by locating the folder:
* **On Windows:** *C:/Users/%USERNAME%/AppData/Roaming/Mozilla/Firefox/Profiles/%LETTERS_AND_NUMBERS%.default/*.
* **On Linux:** *~/.mozilla/firefox/%LETTERS_AND_NUMBERS%.default/*.<br>
* **On Mac:** *~/Library/Application Support/Firefox/Profiles/%LETTERS_AND_NUMBERS%.default/*.<br>
In that folder, create the folder: "chrome", if it doesn't exist already.
In the "chrome" folder, put the file "userChrome.css".
3. Change the style of Tree Style Tab.
Under *Tools->Addons->Extensions->Tree Style Tab options->Advanced*, you can write your own style rules.
Copy and paste all of the style rules (css) below, for a compact, dark-brown look. You can change the colors, colorA to colorG, the tab-height, and the font-size to your liking.
4. Change Tree Style Tab appearance:
Under *Tools->Addons->Extensions->Tree Style Tab options->Appearance*, choose the appearance which works best for you.
"Metal" and "Sidebar" do not work very well with the style rules below.
You'll most likely also want to disable "animation effects".

```css
:root {
  --colorA: #ecff6b;
  --colorB: #a4ffac;
  --colorC: #b4b4b4;
  --colorD: #5ceaff;
  --colorE: #514350;
  --colorF: #281f1a;
  --colorG: green;
  --tab-height: 19px;
  --font-size: 11px;
  background-color: var(--colorF);
}

.tab {
color: white;
background-color: var(--colorE);
height: var(--tab-height);
border-top: none;
border-right: none;
border-left: none;
border-bottom: 1px solid var(--colorF);
}

.label {
font-size: var(--font-size);
}

.tab.active .label {
color: black;
}

.tab .counter {
 color: var(--colorD);
}

.tab.active .twisty
{
 color: var(--colorG);
}

.tab.active {
color: black;
background-color: var(--colorA);
}

.tab.active:hover {
 background-color: var(--colorA);
}

.tab:hover, .tab:not(.active):hover {
  color: black;
  background-color: var(--colorB);
}

.tab.unread .label {
  font-style: italic;
}

.tab.discarded {
  color: var(--colorC);
  background-color: black;
  border-top: none;
  border-bottom: 1px solid black;
}

.tab.private-browsing .label:before {
  content: "🕶";
}
```
