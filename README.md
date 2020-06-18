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
Looking for a replacement, I found that Tree Style Tab by Piro was working in Firefox Quantum.
By default, with that extension, the tabs are very large and too bright.
It takes 5 steps to get the proper vertical tabs experience.

1. <b>Install the "Tree Style Tab" addon for Firefox.</b> It can be downloaded from <a target="_blank" href="https://addons.mozilla.org/en-US/firefox/addon/tree-style-tab/">here</a>.
2. <b>Enable Firefox dark theme.</b><br>
Open *Tools->Addons->Themes*. Press enable for the "Dark" theme.
3. <b>Disable the horizontal tabs and the Sidebar Header</b> (large field above your vertical tabs).<br>
You'll first need to open your Firefox profile folder. In Firefox, open the url: "about:support".<br>
There's an entry titled *Application Basics->Profile Folder* or *Application Basics->Profile Directory*. Clicking the button "Open Folder" should open the profile folder. If that doesn't work, navigate to the listed directory in your file browser.

In the profile folder, create a folder named "chrome".
Then create a file called "userChrome.css" in the chrome folder.

Paste this content into your userChrome.css file:
```css
@namespace url("http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul");

#TabsToolbar {
  visibility: collapse;
}

#sidebar-box[sidebarcommand="treestyletab_piro_sakura_ne_jp-sidebar-action"] #sidebar-header {
  visibility: collapse;
}
```
Restart Firefox to apply the userChrome CSS.

4. <b>Change the style of Tree Style Tab.</b><br>
Under *Tools->Addons->Extensions->Tree Style Tab options->Advanced*, you can write your own style rules.
Copy and paste the style rules (CSS) below, for a compact, dark/gray look. You can change the colors: colorA to colorG, the tab-height, and the font-size to your liking. As an alternative to using these many style rules, you can keep it simple by using only the two rules at the bottom of the page, which only make your tabs compact. Then use the "Plain Dark" appearance (step 5).
5. <b>Change Tree Style Tab appearance:</b><br>
Under *Tools->Addons->Extensions->Tree Style Tab options->Appearance*, choose the appearance which works best for you. "Metal" and "Sidebar" do not work well with the CSS below.
You'll most likely also want to disable "animation effects".

You're done. It should be working now!<br>
Remember that if you close the vertical tabs area by mistake, or you use the area to show bookmarks, you can always press F1 to bring the tabs back again. Have fun.

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
