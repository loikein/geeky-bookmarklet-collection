# Bookmarklet Collection

Goals:

- List
- Breakdown
- Learn

## (Maybe Useful) References

[Making Bookmarklets](https://gist.github.com/caseywatts/c0cec1f89ccdb8b469b1)

[Awesome\-Bookmarklets/README\.md at master · Priyank\-Vaghela/Awesome\-Bookmarklets](https://github.com/Priyank-Vaghela/Awesome-Bookmarklets/blob/master/README.md)

[marcobiedermann/awesome\-bookmarklets: Awesome collection of helpful bookmarklets](https://github.com/marcobiedermann/awesome-bookmarklets)

[Awesome Bookmarklets](https://codepen.io/thesturs/pen/xbRomP)


## [Google Translate](https://translate.google.com/)

Anything to English

```javascript
javascript:location='http://translate.google.com/translate?langpair=auto|en&u='+encodeURIComponent(location)
```

Anything to Chinese

```javascript
javascript:location='http://translate.google.com/translate?langpair=auto|zh&u='+encodeURIComponent(location)
```

another vertion:

```javascript
javascript: var%20t=((window.getSelection&&window.getSelection())%7C%7C(document.getSelection&&document.getSelection())%7C%7C(document.selection&&document.selection.createRange&&document.selection.createRange().text)); var%20e=(document.charset%7C%7Cdocument.characterSet);if(t!='')%7Blocation.href='http://translate.google.com/?text='+t+'&hl=zh-CN&langpair=auto%7Czh-CN&tbb=1&ie='+e; %7Delse%7Blocation.href='http://translate.google.com/translate?u='+encodeURIComponent(location.href)+'&hl=zh-CN&langpair=auto%7Czh-CN&tbb=1&ie='+e;%7D;
```

## [MathJax bookmark](https://www.math.ucla.edu/~robjohn/math/mathjax.html)

start ChatJax

> "start ChatJax" installs MathJax and starts a loop that renders LaTeX as needed.  
> This is intended for use in chat, where the contents of the page are not static. 
> Reloading the page will stop the loop, so the bookmark needs to be run again. 

```javascript
javascript:(function(){if(window.MathJax===undefined){var%20script%20=%20document.createElement("script");script.type%20=%20"text/javascript";script.src%20=%20"https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS_HTML";var%20config%20=%20%27MathJax.Hub.Config({%27%20+%20%27extensions:%20["tex2jax.js"],%27%20+%20%27tex2jax:%20{%20inlineMath:%20[["$","$"],["\\\\\\\\\\\\(","\\\\\\\\\\\\)"]],%20displayMath:%20[["$$","$$"],["\\\\[","\\\\]"]],%20processEscapes:%20true%20},%27%20+%20%27jax:%20["input/TeX","output/HTML-CSS"]%27%20+%20%27});%27%20+%20%27MathJax.Hub.Startup.onload();%27;if%20(window.opera)%20{script.innerHTML%20=%20config}%20else%20{script.text%20=%20config}%20document.getElementsByTagName("head")[0].appendChild(script);(doChatJax=function(){window.setTimeout(doChatJax,1000);MathJax.Hub.Queue(["Typeset",MathJax.Hub]);})();}else{MathJax.Hub.Queue(["Typeset",MathJax.Hub]);}})();
```

render MathJax

> "render MathJax" installs MathJax and renders LaTeX once per execution.  
> This is intended for use on web pages where the contents of the page are static. 

```javascript
javascript:(function(){if(window.MathJax===undefined){var%20script%20=%20document.createElement("script");script.type%20=%20"text/javascript";script.src%20=%20"https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS_HTML";var%20config%20=%20%27MathJax.Hub.Config({%27%20+%20%27extensions:%20["tex2jax.js"],%27%20+%20%27tex2jax:%20{%20inlineMath:%20[["$","$"],["\\\\\\\\\\\\(","\\\\\\\\\\\\)"]],%20displayMath:%20[["$$","$$"],["\\\\[","\\\\]"]],%20processEscapes:%20true%20},%27%20+%20%27jax:%20["input/TeX","output/HTML-CSS"]%27%20+%20%27});%27%20+%20%27MathJax.Hub.Startup.onload();%27;if%20(window.opera)%20{script.innerHTML%20=%20config}%20else%20{script.text%20=%20config}%20document.getElementsByTagName("head")[0].appendChild(script);}else{MathJax.Hub.Queue(["Typeset",MathJax.Hub]);}})();
```

> Useful when rendering is slow while editing questions and answers. 

rendering on

```javascript
javascript:(function(){MathJax.Hub.queue.pending=0;MathJax.Hub.Queue(["Typeset",MathJax.Hub,"wmd-preview"]);})();
```

rendering off

```javascript
javascript:(function(){MathJax.Hub.queue.pending=1;})();
```

## [Webpage archive](https://archive.is/)

```javascript
javascript:void(open('https://archive.is/?run=1&url='+encodeURIComponent(document.location)))
```

