# Compact dark-brown style for Tree Style Tab by Piro.

With the update to Firefox Quantum, I was no longer able to use Tab Tree by Sergey Zelentsov.
Looking for a replacement, I found that Tree Style Tab by Piro (which I used before Tab Tree) is working in Firefox Quantum.
By default, with that extension, the tabs are very large and too bright.
It takes 3 steps to get the proper vertical tabs experience.
1. Disable the horizontal tabs.
**On Windows:** You disable the horizontal tabs by locating the folder:
*C:/Users/%USERNAME%/AppData/Roaming/Mozilla/Firefox/Profiles/%LETTERS_AND_NUMBERS%.default/*.
In that folder, if it doesn't exist already, create the folder: "chrome".
In the "chrome" folder, put the file "userChrome.css".
2. Change Tree Style Tab appearance:
Under *Tools->Addons->Extensions->Tree Style Tab options*, choose either "Vertigo" or "Mixed" appearance (for compatibility with step 3).
3. Change the style of Tree Style Tab.
Under *Tools->Addons->Extensions->Tree Style Tab options*, you can write your own style rules.
Copy and paste all of the style rules below, for a compact, dark-brown look. You can, of course, change the colors to your liking:

```css
:root {
  --tab-height: 19px;
  background-color: #281f1a;
}

.tab {
color: white;
background-color: #514350;
height: var(--tab-height);
border-top: none;
border-right: none;
border-left: none;
border-bottom: 1px solid #281f1a;
}

.tab .label {
font-size: 11px;
}

.tab.active{
background-color: #ecff6b;
}

.tab.unread .label {
  font-style: italic;
}

.tab.discarded {
  color: #b4b4b4;
  background-color: black;
  border-top: none;
  border-bottom: 1px solid black;
}

.tab.private-browsing .label:before {
  content: "🕶";
}
```
