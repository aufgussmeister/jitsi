# LIBRERIA
```
<script src='https://jitsi.xxxxxxx.it/external_api.js'></script>
```

# DIV dove viene inniettato Jitsi

```
<div id="meet" ref="meet"></div>
```

# DEFINIZIONE PARAMETRI CON PANNELLO DI CONTROLLO
```
const options : {
        width: "100%",
        height: 500,
        interfaceConfigOverwrite: { filmStripOnly: false },
        parentNode: document.querySelector('#meet'),
        roomName: "room Name",
        userInfo: {displayName: "User Name"}
      }

const domain : 'jitsi.xxxxxx.it';
```
# DEFINIZIONE PARAMETRI CON SOVRASCRITTURA IMPOSTAZIONI

[config file](https://github.com/jitsi/jitsi-meet/blob/master/config.js)

```
options : {
        roomName: false,
        width: "100%",
        height: 500,
        interfaceConfigOverwrite: { filmStripOnly: false },
        parentNode: document.querySelector('#meet'),
        configOverwrite: {toolbarButtons: [], DISABLE_JOIN_LEAVE_NOTIFICATIONS: true, DISABLE_FOCUS_INDICATOR: true} //tolti comandi 
        roomName: "room Name",
        userInfo: {displayName: "User Name"}
      }
const domain : 'jitsi.aznext.it';
```

# AVVIO CALL
```
const  video = new JitsiMeetExternalAPI(domain, options);
 ``` 

# INIZIO REGISTRAZIONE
```
video.executeCommand('startRecording', {
    mode: 'file'
});
```

# FINE REGISTRAZIONE
```
video.executeCommand('stopRecording','file');
```

# CHIUSURA CHIAMATA
```
video.disconnect(); 
or
video.dispose();
```