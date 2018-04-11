# Creating an ERC20-Token
Go through easy process on creating your token.

---

1. **Download & install**
```bash
https://brave.com/download/
```
After downloading brave browser, go to metamask and download it as well.

```bash
https://metamask.io/
```

Continue by running git clone from our target directory:

```bash
git clone https://github.com/brave/browser-laptop.git  
```

This step shouldn’t take long. Once completed, install the dependencies.

```bash
cd browser-laptop  
npm install  
```

Open two terminals, and run npm run watch from the first. This launches the webpack developer server. Once the server has been stood up, switch to the second terminal, and run npm start. Within a couple of moments, Brave should appear.

Downloading Chrome Extensions

Open a new terminal from the browser-laptop directory, and run the following command:

```bash
npm install -g chrome-ext-downloader 
```

Once installed, it’s time to get our extension. We’ll want to make sure we install the extension into app\extensions\:

```bash
cd app\extensions  
ced mefhakmgclhhfbdadeojlkbllmecialg  
```

At this point, we should have three folders in app\extension\: brave, torrent, and tabbycat.

We now need to register and load the Tabby Cat extension on startup. To do this, open the app\extensions.js file, and locate the following lines:

// Manually install the braveExtension and torrentExtension

```bash
extensionInfo.setState(config.braveExtensionId, extensionStates.REGISTERED)  
loadExtension(config.braveExtensionId, getExtensionsPath('brave'), generateBraveManifest(), 'component')  
```

Beneath these lines, insert the following:

// Enable Tabby Cat

```bash
extensionInfo.setState('tabbycat', extensionStates.REGISTERED)  ```

```bash
loadExtension('tabbycat', getExtensionsPath('tabbycat'))  
```

The first line is a simple comment for helping us find our way back if we ever get lost. The second line contains the extensionInfo.setState method; this registers our extension. The loadExtension method tells Brave where to locate the extension manifest.