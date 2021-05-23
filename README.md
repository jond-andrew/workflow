# workflow 

This is a collection of snippets, settings and resources related to setting up a dev env or "workflow". 

![My iterm demo](/img/iterm.png)

> Note: This doc is currently in *draft* status.

### Additional Onboarding Gudies

- [New Hire Checklist - Onboarding Email](https://docs.google.com/document/d/1oWpsuNplzDFAaD5Ks59aquoZ1RIlf7z6heVwaX7XiaQ/edit?usp=sharing)
- [O11y and Synthetic Monitoring Environment Setup - Team 404](https://confluence.splunk.com/display/PROD/O11y+and+Synthetic+Monitoring+Environment+Setup)
- [O11y App Developer’s Guide - Signal Fx](https://docs.google.com/document/d/1kDWCuY5y0IokbSkpx-edgyjwl3hl1YRoX0JixuiH6Z4/edit?usp=sharing)
- [Setting-up Your New Splunk Mac Laptop](https://docs.google.com/document/d/1ry-AGxdPO98Hlzq6cNDZPBlodJIQwOckDNXY5sVdy1Q/edit?usp=sharing)

### Apps

- iTerm2
- VSCode (?)
- Sublime Text 4 (?)

### Command Line or Brew Install Utils

- [Oh My ZSH](https://github.com/ohmyzsh/ohmyzsh)
- [Homebrew](https://brew.sh/), MacOS package manager
- [Amethyst](https://ianyh.com/amethyst/), automagical window tiler 
- [z](https://github.com/rupa/z), easily jump to visited directories
- [n](https://github.com/tj/n), if you already have `node`
- [n-install](https://github.com/mklement0/n-install), if you do not have `node`
- [neofetch](https://github.com/dylanaraps/neofetch/wiki/Installation), display system info

> Amethyst Preferences, Mouse: mouse follows focus. Floating: Automatically float App: iTerm2

### Oh My ZSH and related config

```
ZSH_THEME="agnoster"
```

Enable Agnoster's glyphs. Clone (Powerline Fonts)[https://github.com/powerline/fonts] and run:
```
./install.sh
```

Update the prompt with a little bit of fun:
```
prompt_context() {
  if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
    prompt_segment green black "%(!.%{%F{yellow}%}.) ༼つ◕_◕༽つ"
  fi
}
```

Enable `z` 
```
source /usr/local/etc/profile.d/z.sh
```


Create a symlink for opening Sublime:
```
ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/sublime
```
[Source](https://olivierlacan.com/posts/launch-sublime-text-3-from-the-command-line/)

Useful: [zsh GitHub commands Cheatsheet](https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet)



#### iTerm 2

Manual instructions for setting up iTerm. In iTerm Preferences

- General
	- Closing: Quit when all windows are closed
	- Closing: Uncheck confirm quit
	- Selection: Check double-click performs smart select
	- Window: Uncheck adjust window when changing font size
- Appearance
	- Theme: Minimal
	- Window: Uncheck show window number in title bar
	- Window: Check Hide Scrollbars
- Profiles
    - General: Title Dropdown: select only "PWD", clear other selections
    - General: Working Directory: select "Reuse previous session's directory"
	- Colors: Color Preset: Solarized Dark
	- Text: Font: Fira Mono for Powerline
	- Text: Font size: 21
	- Window: Style: Full-Width Top of Screen
	- Window: Space: All Spaces 
	- Keys: Hotkey Window: check "A hotkey opens..."
		- Hotkey
		- Double-tap key: Command (?)
		- On Dock icon click: Show this hotkey window
	- After Hotkey setup, head back to General tab and:
        - Startup: select in "Window restoration policy" dropdown, "Only Restore Hotkey Window"
	    - (Note: there's now a Hotkey section in the main "Keys", so it is possible to do this outside of Profiles)
- Keys 
    - Select menu item: Restart Session Hotkey: `shift + ⌘ + r`
- Advanced
    - Session: Suppress restart confirmation alert: Yes
    - Tabs: Custom tab label size: 16
    - Tabs: Preferred tab width when tabs are equally sized: 280
    - Tabs: Use custom font size for tab labels?

Silence "Last Login" message for new tab. `cd ~`, then: 
```
touch .hushlogin
```

### Zoom "Live Mic" Menu Bar

A slightly silly utility to keep track of a live mic in meetings.

![Animation of zoom menu bar toggling](img/zoom-swiftbar.gif)

- SwiftBar https://github.com/swiftbar/SwiftBar
	- `brew install swiftbar`
	- Cmd + space, run `swiftbar`
	- Choose a plugins folder, like `Documents/Swiftbar`
	- Download the Zoom status scripts: https://github.com/nickjvturner/SwiftBar-Zoom-Plugins
	- Place the downloaded plugins into the freshly selected plugins folder
	- Allow Accessibility permissions, and once permissions are correctly configured, launch Zoom, start a meeting and test the information output to your menubar.

> Note: the implementation of this could be better, but it works for now. The script isn't perfectly responsive and may have some overhead. 

### App Store

- Things 3
- iA Writer

### Favorite Splunk Value:

Disruptive
> We strive to lead, not follow, while continuing to disrupt the market.  We never say "Don't change it if it's not broken." We're always looking at things from different angles with an eye for how we can do it better, faster and more efficiently.

A friend told me my motto should be: "If it's not broken, fix it 'til it is".

## Hardware

- Keyboard: (ZSA Moonlander)[https://www.zsa.io/moonlander/]
    - A powerful and easily programmable split ergo, quickly becoming my favourite keyboard
    - (Link to my configuration)[https://configure.zsa.io/moonlander/layouts/eW95r/latest/0]
- Mouse: (Glorious Model O)[https://www.pcgamingrace.com/products/glorious-model-o-white], wonderful, super light weight, comfortable, with a cord that never catches
- Microphone: Shure [SM7B](https://www.shure.com/en-US/products/microphones/sm7b), best in the game, make sure you have a USB Audio Interface and a definitely pick up a preamp
- Audio Interface: [Scarlett Solo](https://focusrite.com/en/usb-audio-interface/scarlett/scarlett-solo)
- Preamp: [Cloudlifter](https://www.sweetwater.com/store/detail/CL1Cloud--cloud-microphones-cl-1-cloudlifter-1-channel-mic-activator)
- Green Screen: [Elgato Chroma Key](https://www.elgato.com/en/green-screen)
- Lights: [Neewer Ring Light](https://www.amazon.com/Neewer-Ring-Light-Kit-Self-Portrait/dp/B01LXDNNBW), and [Neewer 2 Pack Dimmable LEDs](https://www.amazon.com/Neewer-Packs-Dimmable-Bi-Color-Lighting/dp/B072Q42GXQ/ref=sr_1_9?dchild=1&keywords=neewer&qid=1621782731&s=electronics&sr=1-9)


#### Keyboard Notes / Todo:

- Consider swapping the space bar and L1 on the piano keys? The space bar is often a "tap", and L1 is a hold, slightly awkward, but space is used more often... Tough call.
- Dedicated copy & paste
- Consider unbinding pinky key enter and L1, to force thumb key usage.
- Add a Zoom unmute key of some sort. 
- Consider better `[]()` 
- Add right hand arrow keys, as they would allow better modifier combinations, possibly `IJKL`, plus and parens are the only things to move
- unbind left hand MO1.

> Possibly add changelog here. No more left shift is really a tough one to get used to!

### Notes & Scratch Pad  

TODO: Collect all of the various Set up instructions in a list with title/link

> Section on the packages github could be a little clearer / cleaner
> To accept the invitation from incognito gmail for splunk packages account
 
```
npm login --registry=https://npm.pkg.github.com

Username: jond-andrew
Password:
Email: (this IS public) jond@splunk.com
Logged in as jond-andrew on https://npm.pkg.github.com/.
```

Gerrit info
https://signalfuse.atlassian.net/wiki/spaces/SEP/pages/192446466/Gerrit+Code+Review#GerritCodeReview-Clonerepository

jond-splk-packages
jond+splk+packages@splunk.com

ssh-keygen -t ed25519 -C "jond@splunk.com"

git clone ssh://jond-andrew@gerrit.corp.signalfx.com:29418/signalfx/apm-app-web && scp -p -P 29418 jond-andrew@gerrit.corp.signalfx.com:hooks/commit-msg apm-app-web/.git/hooks/

##### Staging:

reset your Password

"lab" versus dev versus staging

super powers.

local config patch

const localConfig = {
    syntheticsCSS: 'http://localhost:4200/syntheticsModule.css',
    syntheticsJS: 'http://localhost:4200/syntheticsModule.js'
};

webpack.config.js

/api/helpers/config.ts

should be managed by .env added to .gitignore

git config --list --show-origin

git config --global user.email "jond@splunk.com"
git config --global user.name "Andrew Davis"


To get access to Cypress - go into GroupID (its an okta chicklet), and add yourself to the “sg-okta-cypress-users” group.  It’ll get approved by the admin (usually within a day) and you’ll get the okta chicklet soon after. (edited) 