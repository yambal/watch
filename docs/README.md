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
# <span class="now-watch" id="title-watch">&#xe262;</span> Watch (font)
## Download
- [TrueType Font (.ttf)](fonts/watch.ttf)
- [Embedded OpenType (.eot)](fonts/watch.eot)
- [Web Open Font Format (.wof)](fonts/watch.woff)

# Guide
<script>
  function onSet() {
    var inputElement = document.getElementById("time")
    var checkElement = document.getElementById("check")
    var resultElement = document.getElementById("result")
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
      = html exsample : <code><span class="watch">${unicode}</span><code>`
      resultElement.innerHTML = unicode
    }
    return
  }
</script>
<input id="time" type="time">
<button onclick="onSet()">set</button>
<pre id="check"></pre>
<div id="result" class="watch"></div>


## Licence
<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://yambal.github.io/watch/">Watch</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://twitter.com/YamamotoJune">June YAMAMOTO</a> is licensed under <a href="http://creativecommons.org/licenses/by-nd/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution-NoDerivatives 4.0 International<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nd.svg?ref=chooser-v1"></a></p>

<script>
  function setNow() {
    const min = (new Date().getTime()/60000) % 720
    const hex = ("000" + (min).toString(16)).slice(-3)
    const unicode = `&#xe${hex};`
    const elements = document.getElementsByClassName("now-watch")
    elements.forEach((element) => {
      element.innerHTML = unicode
    })
  }

  setNow()
</script>