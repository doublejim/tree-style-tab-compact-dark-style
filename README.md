# Compact dark Firefox style for Tree Style Tab by Piro.

### End result from following this guide:
<table>
    <tr>
      <td align="center">
        With all the style rules enabled:
      </td>
      <td align="center">
        Or a simple, compact Plain Dark:
      </td>
    </tr>
    <tr>
      <td>
      <img alt="screenshot" src="https://raw.githubusercontent.com/doublejim/tree-style-tab-compact-dark-style/master/screenshot.png"/>
      </td>
      <td>
        <img alt"screenshot/only compact" src="https://raw.githubusercontent.com/doublejim/tree-style-tab-compact-dark-style/master/screenshot-only-compact.png"/>
      </td>
    </tr>
</table>

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
* **On Mac:** *~/Library/Application Support/Firefox/Profiles/%LETTERS_AND_NUMBERS%.default/*.<br><br>
In that folder, create the folder: "chrome", if it doesn't exist already.
In the "chrome" folder, put the file "userChrome.css".
3. Change the style of Tree Style Tab.
Under *Tools->Addons->Extensions->Tree Style Tab options->Advanced*, you can write your own style rules.
Copy and paste the style rules (css) below, for a compact, dark/gray look. You can change the colors: colorA to colorG, the tab-height, and the font-size to your liking. As an alternative to using these many style rules, you can keep it simple by using only the two rules at the bottom of the page, which only make your tabs compact. Then use the "Plain Dark" appearance (step 4).
4. Change Tree Style Tab appearance:
Under *Tools->Addons->Extensions->Tree Style Tab options->Appearance*, choose the appearance which works best for you. "Metal" and "Sidebar" do not work well with the css below.
You'll most likely also want to disable "animation effects".

```css
:root {
  --colorA: #ecff6b;
  --colorB: #6affda;
  --colorC: #b4b4b4;
  --colorD: #5ceaff;
  --colorE: #514350;
  --colorF: #281f1a;
  --colorG: green;
  --tab-height: 19px;
  --font-size: 11px;
  background-color: var(--colorF);
}

:root.simulate-svg-context-fill .closebox::after {
  background: white;
}

:root.simulate-svg-context-fill .tab.active .closebox::after {
  background: black;
}

:root.simulate-svg-context-fill .tab:hover .closebox::after {
  background: black;
}

:root.simulate-svg-context-fill .tab.active .sound-button::after {
  background: black;
}

:root.simulate-svg-context-fill .tab:hover .sound-button::after {
  background: black;
}

.tab {
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

.tab .label {
  color: white;
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

.tab:hover .label {
 color: black;
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

## Alternatively: only make the tabs compact.

The following css will only make the tabs more compact, without changing any of the colors.
Works for all appearances.
```css
.tab {
height: 19px;
}

.label {
font-size: 11px;
}
```
