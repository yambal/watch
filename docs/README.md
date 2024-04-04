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
  }
  </style>
# <span class="watch now-watch">&#xe262;</span> Watch (font)
Analog clock icon font.
It contains 720 minute icons for 12 hours (720 minutes) from 0:00 to 11:59, and 24 hours can be expressed by a single character.
## Download
- [TrueType Font (.ttf)](fonts/watch.ttf)
- [Embedded OpenType (.eot)](fonts/watch.eot)
- [Web Open Font Format (.wof)](fonts/watch.woff)

## Icon Table
The font corresponding to each time is converted to hexadecimal minutes elapsed since 0:00 (or 12:00) and assigned to ``&#xe000;`` to ``&#xe2cf;`` in the Private Use Area of Unicode
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