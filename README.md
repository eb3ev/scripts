# Scripts

Put in ~/.profile

```sh
export SCRIPTS_HOME=".../scripts"
export SCRIPTS_BIN="$SCRIPTS_HOME/bin"

export BOOKMARKS=".../..." # Path to bookmarks file
export BOOKMARK_GROUPS=".../..." # Path to directory

export SEARCH_ENGINES=".../..." # Path to search engines file

export WALLPAPERS_DIR=".../..." # Path to wallpapers directory
export WALLPAPER_PRESETS=".../..." # Path to wallpaper presets file

export WALLPAPERS_DIR=".../..." # Path to screen layouts file
```

Bookmarks File Example:
```sh
# Bookmark Name ; Bookmark URL

# Example
GitHub/eb3ev/scripts ; https://github.com/eb3ev/scripts
```

For Bookmark Groups, create a file inside BOOKMARK_GROUPS with the URLs inserted line by line.

Search Engines File Example:
```sh
# Search Engine Name ; Search Engine Prefix URL

# Example
sd|DuckDuckGo ; https://duckduckgo.com/?q=
# Naming Tips:
# * sd| is added to use as a keyword on searching the search engines menu
```
Wallpaper Presets File Example:
```sh
# Preset Name ; <Hostname> ; <Screen Count> ; <XWallpaper command>

# Example
Black ; myLaptop ; 1 ; xwallpaper --output eDP --zoom '/usr/share/wallpapers/black.png'
```

Screen Layouts File Example:
```sh
# Layout Name ; <Hostname> ; <Screen Count> ; <XRandr command> ; <XWallpaper command>

# Examples
Single [1920x1080] ; myLaptop ; 1 ; xrandr --output eDP --primary --mode 1920x1080 --pos 0x0 --rotate normal --output HDMI-A-0 --off ; xwallpaper --output eDP --zoom '/usr/share/wallpapers/black.png'
Mirrored [1920x1080]:[1920x1080] ; myLaptop ; 2 ; xrandr --output eDP --primary --mode 1920x1080 --pos 0x0 --rotate normal --output HDMI-A-0 --mode 1920x1080 --pos 0x0 --rotate normal ; xwallpaper --output eDP --zoom '/usr/share/wallpapers/black.png'
Right [1920x1080]:1920x1080 ; myLaptop ; 2 ; xrandr --output eDP --primary --mode 1920x1080 --pos 0x0 --rotate normal --output HDMI-A-0 --mode 1920x1080 --pos 1920x0 --right-of eDP --rotate normal ; xwallpaper --output eDP --zoom '/usr/share/wallpapers/black.png' --output HDMI-A-0 --zoom '/usr/share/wallpapers/black.png'
Above [1920x1080]^1920x1080 ; myLaptop ; 2 ; xrandr --output eDP --primary --mode 1920x1080 --pos 0x0 --rotate normal --output HDMI-A-0 --mode 1920x1080 --pos 0x1080 --above eDP --rotate normal ; xwallpaper --output eDP --zoom '/usr/share/wallpapers/black.png' --output HDMI-A-0 --zoom '/usr/share/wallpapers/black.png'
# Naming Tips:
# * [Resolution] indicates the primary display
# * [...]:... indicates the monitor to the right
# * [...]^... indicates the monitor above
```

Note:
```sh
# Values are separated by ' ; '
```
## Dependencies

* xwallpaper
* pulseaudio
* xclip
* simple-mtpfs
* fuse2
* udisks2
* wmctrl
* xdotool
* colorpicker (https://github.com/Jack12816/colorpicker)

* dmenu (Specific patched DMenu required for top_window, center_window, bottom_window options)
* fzf
* alacritty
* xterm
* lf

For set_wm, XInit to launch XServer must be used. And in your xinitrc, grab the WM from ~/.config/wmrc

