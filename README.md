# video-js-record-vue-test (record-app)
####_Test code of recording video_ with JS and Vue.js and saving locally as a file based on: 
 - Video.js Record (https://www.npmjs.com/package/videojs-record)
 - recordRTC (https://www.npmjs.com/package/recordrtc)
 - webrtc-adapter (https://github.com/webrtc/adapter)
 - saving video locally as a file https://stackoverflow.com/questions/19327749/javascript-blob-filename-without-link
<br><br>

---

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

<br>

---
---

<br>

## NOTES of research and tests (PL version)
1. **RecordRTC** (https://www.npmjs.com/package/recordrtc)	
Większość rozwiązań dla developerów oparta jest o ten pakiet rozwijany przez gościa z długim starzem w obsłudze video (w innych tego typu projektach Mauz Kahn zaangażowany od 2013r.)	
Ma możliwość nagrywania poprzez GIF’y!!! :)	
Niestety to rozwiązanie oparte jest o natywne MediaStream/getUserMedia (nie działa dobrze na wszystkich przeglądarkach)	
	
2. **webrtc-adapter** (https://github.com/webrtc/adapter) - SUPPORT RÓŻNYCH PRZEGLĄDAREK	
Przede wszystkim dla desktopowych przeglądarek Chrome, Edge, Firefox, Safari	
W przypadku braku obsługi MediaStream/getUserMedia uruchamia nagrywanie klatak po klatce przez gif’y za pomocą RtcTrackEvent (tak się dzieje też dla Safari)	
	
3. Video.js Record (https://www.npmjs.com/package/videojs-record) - INTEGRACJA & VUE.JS (i inne biblioteki reaktywne)	
Biblioteka oparta o **__RecordRTC i webrtc-adapter (tzn. o natywne rozwiązania JS: MediaStream/getUserMedia i RtcTrackEvent)__**. Biblioteka integrująca, posiadająca obsługę wielu przeglądarek, posiadająca obsługę Reacta & Vue	
Nie widzę, aby obsługiwał urzadzenia mobilne, ale test na Androidzie z Chrome wyszedła pozytywny	
Twórca (Thijs Triemstra Groningen NL) szybko odpowiada na issues, rozwija projekt, stworzył niespotykanie dobrą dokumentację!!! :)	
Test nagrywania i odtwarzania (na jakiejkolwiek przeglądarce, dla znalezionej biblioteki Videojs-record): https://github.com/collab-project/videojs-record#examples	https://github.com/collab-project/videojs-record#examples
Przetestowano wg powyższego z wynikiem: 	
- pozytywny:	
    - Ubuntu 18.04.4 LTS: Chrome 81, Mozilla Firefox 75	
    - Windows 10: Chrome 81, Mozilla Firefox 75, Edge 81	
    - IOS: Safari 12 / 13, Brave	
    - Android 8.0.0: Chrome mobile 81, Android natywny	
 - negatywny:	
    - Windows 10: Internet Explorer 11	
	
	
<br>

>####Dodatkowe informacje techniczne:
>	
> - Provides cross-browser support for getUserMedia and other browser APIs used in this plugin.	https://github.com/webrtc/adapter
> - Lista wtyczek do przeglądarek	https://github.com/collab-project/videojs-record/wiki/Browser-support
> - Wyjasnienie ograniczeń mediaStream and local storage	https://stackoverflow.com/questions/17331531/html5-capture-and-save-video
> - Wspieranie MediaStrem przez przeglądarki	https://caniuse.com/#search=MediaStream
> - Wspieranie RtcTrackEvent przez przeglądarki	https://caniuse.com/#search=RtcTrackEvent
