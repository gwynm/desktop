# Standard Velocity

This is a forked version, used with the forked Standard Notes core.

It'll pull the forked core itself (in package.json) initially, but if you're doing development, you probably want to rm -rf app/node_modules/standard-notes-web and ln -s ~/dev/standard-velocity-web app/node_modules/standard-notes-web. Then run npm build on the web side, then npm run dist-linux on the desktop side, to make a new version after changes.


## How do I add the app to the launcher?

On Ubuntu 19 this is weirdly hard. When you run the AppImage it'll pop up asking whether you want to integrate, but clicking 'Yes' won't do anything. Instead, download and install 'appimaged', then move the AppImage into ~/Applications. From there it should show up in the 'grid launcher', and you can run it, then right-click it in the dock and hit 'add to favourites' in order to keep it in the dock.

Behind the scenes, it appears that something like ./.local/share/applications/appimagekit_d8fc9619521145653f35139fefcf25a6-Standard_Velocity.desktop is created.


# Standard Notes

This application makes use of the core JS/CSS/HTML code found in the [web repo](https://github.com/standardnotes/web). For issues related to the actual app experience, please post issues in the web repo.

## Running Locally

```
npm run setup
npm run start
```

## Building

Build for all platforms:
```
electron-packager . "Standard Notes" \
  --platform=all \
  --icon=icon/icon \
  --overwrite \
  --osx-sign='Mac Developer ID Application: xxx' \
  --out=dist
```

or

- `npm run dist`

or

- `npm run dist-win`
- `npm run dist-linux`
- `npm run dist-mac`

## Installation

On Linux, download the latest AppImage from the [Releases](https://github.com/standardnotes/desktop/releases/latest) page, and give it executable permission:

`chmod u+x standard-notes*.AppImage`

## Alternative Downloads

The Standard Notes desktop client is also available through a variety of package managers:

* [unofficial] **AUR:** [sn-bin](https://aur.archlinux.org/packages/sn-bin/), binary package, currently maintained by [JoshuaRLi](https://github.com/JoshuaRLi)
* [unofficial] **AUR:** [standardnotes-desktop](https://aur.archlinux.org/packages/standardnotes-desktop/), non binary package - built from source, currently maintained by [danielhass](https://github.com/danielhass)
