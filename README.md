# electron-node-red-blockstack

Currently still under construction, but this should be a Blockstack integrated Electron contained Node-Red dapp kit once done.

Video of 1st version of the repo app running: https://youtu.be/zj-jCE9YhYg

The default flows are basic flows for talking to Blockstack locally.

We can base off this model and update the package.json file to include required dependencies. (todo)

## To Use

To clone and run this repository you'll need [Git](https://git-scm.com) and [Node.js](https://nodejs.org/en/download/) (which comes with [npm](http://npmjs.com)) and the [Blockstack Browser](https://github.com/blockstack/blockstack-browser/releases) installed on your computer. 


From your command line:

```bash
# Clone this repository
git clone https://github.com/cryptocracy/electron-node-red-blockstack.git

# Go into the repository
cd electron-node-red-blockstack

# Install dependencies with npm
npm install && npm run clean

# Run App with npm
npm start
```

## Search Examples:
Profile: `ryanshea.id`

Project: `pr01-mdf9kesl9v92lclivkrfcgt1.id`  

(note Projects for Souq will have a new `namespace` once the layer 2 token is out)

## TL:DR - building runtimes

On OSX you can run `./buildall` to build binaries of "everything"... maybe...

Run `npm run pack` to create packages for all platforms - these are the files required to run, they are not binary installers.

Builds are created in the `build` directory. Runtimes are created in the `../electron-bin` directory.

**Note**: this was written to work on a Mac... other tools may/will be needed on other platforms.

## Packaging your application

If you want to distribute executables of this project, the easiest way is to use electron-packager:

```
sudo npm install -g electron-packager

# build for OSX 64 bits
electron-packager . Node-RED-Blockstack --icon=nodered.icns --platform=darwin --arch=x64 --out=build --overwrite

# build for Windows 64 bits
electron-packager . Node-RED-Blockstack --icon=nodered.icns --platform=win32 --arch=x64  --out=build --asar=true --overwrite --win32metadata.CompanyName='IBM Corp.' --win32metadata.ProductName='Blockstack Sample App'

# build for Linux 64 bits
electron-packager . Node-RED-Blockstack --icon=nodered.icns --platform=linux --arch=x64 --out=build --overwrite
```

Learn more about Electron and its API in the [documentation](http://electron.atom.io/docs/latest).


### To package as a dmg

`npm run build:osx`

look at `https://github.com/LinusU/node-appdmg`

    sudo npm install -g appdmg

    appdmg appdmg.json ~/Desktop/NodeRED.dmg


### To package as a deb

`npm run build:linux64` or `npm run build:linux32` - for Intel Linux

Look at `https://github.com/jordansissel/fpm`

    fpm -s dir -t deb -f -n node-red-electron-blockstack -v 0.16.2 -m your-email@example.com -a i386 Node-RED-linux-ia32/
    fpm -s dir -t deb -f -n node-red-electron-blockstack -v 0.16.2 -m your-email@example.com -a x86_64 Node-RED-linux-x64/

Use **sudo dpkg -i ...*** to install the correct deb for your architecture.

Use `Node-RED` command to run. Flows are stored in `~/.node-red`.


### To package as an exe

`npm run build:win32` - to build for 32-bit Windows.

`npm run build:win64` - to build for 64-bit Windows.

**Note**: This project was built to run on Mac OSX - To build for windows on other platforms you may need to use other tools.


### Credits
- [electron-node-red](https://github.com/dceejay/electron-node-red)
- [blockstack](https://github.com/blockstack/)
- [node-red](https://github.com/node-red/)
- [electron](https://github.com/electron)


**Disclaimer**: I have no responsiblity, for any functionality or lack there of, in anything you may build from this repo.

