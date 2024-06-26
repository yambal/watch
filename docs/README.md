<style>
  @font-face {
    font-family: 'watch';
    src:  url('fonts/watch.eot?bxjsyq');
    src:  url('fonts/watch.eot?bxjsyq#iefix') format('embedded-opentype'),
      url('fonts/watch.ttf?bxjsyq') format('truetype'),
      url('fonts/watch.woff?bxjsyq') format('woff'),
      url('fonts/watch.svg?bxjsyq#watch') format('svg');
    font-weight: normal;
    font-style: normal;
    font-display: block;
  }
  .watch {
    /* use !important to prevent issues with browser extensions that change fonts */
    font-family: 'watch' !important;
    speak: never;
    font-style: normal;
    font-weight: normal;
    font-variant: normal;
    text-transform: none;
    line-height: 1;

    /* Better Font Rendering =========== */
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;

    font-size: 2rem;
  }
  </style>
<div style="background-color: #6699FF; color: white; padding: 2rem; display: flex; align-items: center; border-radius: 1rem;">
  <div class="watch now-watch" style="font-size:12rem;">&#xe262;</div>
  <h1 style="margin: 0 1rem">Watch (font)</h1>
</div>
This Analog Clock Icon Font includes 720 minute-specific icons covering the 12 hours from 0:00 to 11:59. Each icon represents a different minute, allowing a single character to express 24 hours comprehensively.
## Download
- [TrueType Font (.ttf)](fonts/watch.ttf)
- [Embedded OpenType (.eot)](fonts/watch.eot)
- [Web Open Font Format (.wof)](fonts/watch.woff)

## Icon Table
The icons in the font, representing each minute, are converted to hexadecimal to denote the minutes passed since 0:00 (or 12:00). These are then assigned to Unicode's Private Use Area, ranging from ``&#xe000;`` to ``&#xe2cf;``.

| Time | min → hex | Unicode | HTML Entity | Icon |
| --- | --- | --- | --- | --- |
| 00:00 (12:00) | 0 → 0 | E000 | ``&#xe000;`` | <span class="watch">&#xe000;</span> |
| 00:01 (12:01) | 1 → 1 | E001| ``&#xe001;`` | <span class="watch">&#xe001;</span> |
| 00:02 (12:02) | 2 → 2 | E002 | ``&#xe002;`` | <span class="watch">&#xe002;</span> |
| . | . | . | . | . |
| 00:59 (12:59) | 59 → 3b | E03N | ``&#xe03b;`` | <span class="watch">&#xe03b;</span> |
| 01:00 (13:00) | 60 → 3c | E03C | ``&#xe03c;`` | <span class="watch">&#xe03c;</span> |
| . | . | . | . | . |
| 10:10 (22:10) | 610 → 262 | E262 | ``&#xe262;`` | <span class="watch">&#xe262;</span> |
| . | . | . | . | . |
| 11:59 (23:59) | 719 → 2cf | E2CF | ``&#xe2cf;`` | <span class="watch">&#xe2cf;</span> |

## Sample
### HTML & CSS (Static)
With this sample CSS, you can intuitively display a time-specified icon<br />10:00 = ``watch-1010``
<p class="codepen" data-height="300" data-default-tab="css,result" data-slug-hash="mdgpoZV" data-user="june-yamamoto" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/june-yamamoto/pen/mdgpoZV">
  Untitled</a> by June YAMAMOTO (<a href="https://codepen.io/june-yamamoto">@june-yamamoto</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

### JavaScript & CSS
<p class="codepen" data-height="300" data-default-tab="css,result" data-slug-hash="oNOpVpV" data-user="june-yamamoto" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/june-yamamoto/pen/oNOpVpV">
  Watch (font) Sample</a> by June YAMAMOTO (<a href="https://codepen.io/june-yamamoto">@june-yamamoto</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## Try

<input id="time" type="time" value="10:10">
<button onclick="onSet()">set</button>
<pre id="check"></pre>

## Licence
<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://yambal.github.io/watch/">Watch</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://twitter.com/YamamotoJune">June YAMAMOTO</a> is licensed under <a href="http://creativecommons.org/licenses/by-nd/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution-NoDerivatives 4.0 International<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nd.svg?ref=chooser-v1"></a></p>

<script>
  function onSet() {
    var inputElement = document.getElementById("time")
    var checkElement = document.getElementById("check")
    if(inputElement && checkElement && inputElement.value){
      const [h, m] = inputElement.value.split(":")
      const min = (parseInt(h) * 60 + parseInt(m)) % 720
      const hex = ("000" + (min).toString(16)).slice(-3)

      const sampleUnicode = `&amp;#xe${hex};`
      const unicode = `&#xe${hex};`

      checkElement.innerHTML = `h:${h}, m:${m}
      = ${min}min (minutes elapsed from 00:00 or 12:00)
      = hex: ${hex} (Converted to hexadecimal)
      = unicode: ${sampleUnicode} (Formed as Unicode)
      = html exsample : &lt;span class="watch"&gt;${sampleUnicode}&lt;/span&gt;
      = <span class="watch">${unicode}</span>`
    }
    return
  }

  function setNow() {
    const now = new Date()
    const nowH = now.getHours()
    const nowM = now.getMinutes()
    const min = (nowH * 60 + nowM) % 720
    const hex = ("000" + (min).toString(16)).slice(-3)
    const unicode = `&#xe${hex};`
    const elements = document.getElementsByClassName("now-watch")
    const elementsArr = Array.from( elements )
    elementsArr.forEach((element) => {
      element.innerHTML = unicode
    })
  }

  onSet()
  setNow()
  
  setInterval(setNow, 30000);
</script>
