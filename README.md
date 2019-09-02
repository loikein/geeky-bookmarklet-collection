# Geeky Bookmarklet Collection

Goals:

- List
- Breakdown
- Learn

## (Maybe Useful) References

### Tutorials

[How To Make a Bookmarklet For Your Web Application – BetterExplained](https://betterexplained.com/articles/how-to-make-a-bookmarklet-for-your-web-application/)

[Making Bookmarklets](https://gist.github.com/caseywatts/c0cec1f89ccdb8b469b1)

[Create Bookmarklets \- The Right Way](https://code.tutsplus.com/tutorials/create-bookmarklets-the-right-way--net-18154)

### Other Collections

[37 Bookmarklets to Boost Your Productivity in Chrome, Firefox & Safari \| The Tech Basket](https://www.thetechbasket.com/internet/most-useful-bookmarklets/1398/)

[Topic: bookmarklet](https://github.com/topics/bookmarklet)

[Awesome\-Bookmarklets/README\.md at master · Priyank\-Vaghela/Awesome\-Bookmarklets](https://github.com/Priyank-Vaghela/Awesome-Bookmarklets/blob/master/README.md)

[marcobiedermann/awesome\-bookmarklets: Awesome collection of helpful bookmarklets](https://github.com/marcobiedermann/awesome-bookmarklets)

[Awesome Bookmarklets](https://codepen.io/thesturs/pen/xbRomP)

## [Browser Tab Notepad](https://gist.github.com/loikein/24692da5ef45242a469dbf316b016c48#file-browser-tab-notepad-html)

```html
data:text/html,<html contenteditable style="font-size:1.5rem; line-height:1.4; max-width:60rem; margin:0 auto; padding:4rem;" spellcheck="false"><script>document.documentElement.focus();</script><title>Text Editor</title>
```

## [Google Translate](https://translate.google.com/)

Anything to English

```javascript
javascript:location='http://translate.google.com/translate?langpair=auto|en&u='+encodeURIComponent(location)
```

Anything to Chinese

```javascript
javascript:location='http://translate.google.com/translate?langpair=auto|zh&u='+encodeURIComponent(location)
```

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

## Check [Wayback Machine](http://web.archive.org/)

```javascript
javascript:(function(){%20window.open('http://web.archive.org/web/*/'+location.host)})();
```

```javascript
javascript:void(location.href = 'http://web.archive.org/web/*/' + escape(location.href));
```

## Sort Tables

```javascript
javascript:function toArray (c){var a, k;a=new Array;for (k=0; k<c.length; ++k)a[k]=c[k];return a;}function insAtTop(par,child){if(par.childNodes.length) par.insertBefore(child, par.childNodes[0]);else par.appendChild(child);}function countCols(tab){var nCols, i;nCols=0;for(i=0;i<tab.rows.length;++i)if(tab.rows[i].cells.length>nCols)nCols=tab.rows[i].cells.length;return nCols;}function makeHeaderLink(tableNo, colNo, ord){var link;link=document.createElement('a');link.href='javascript:sortTable('+tableNo+','+colNo+','+ord+');';link.appendChild(document.createTextNode((ord>0)?'a':'d'));return link;}function makeHeader(tableNo,nCols){var header, headerCell, i;header=document.createElement('tr');for(i=0;i<nCols;++i){headerCell=document.createElement('td');headerCell.appendChild(makeHeaderLink(tableNo,i,1));headerCell.appendChild(document.createTextNode('/'));headerCell.appendChild(makeHeaderLink(tableNo,i,-1));header.appendChild(headerCell);}return header;}g_tables=toArray(document.getElementsByTagName('table'));if(!g_tables.length) alert("This page doesn't contain any tables.");(function(){var j, thead;for(j=0;j<g_tables.length;++j){thead=g_tables[j].createTHead();insAtTop(thead, makeHeader(j,countCols(g_tables[j])))}}) ();function compareRows(a,b){if(a.sortKey==b.sortKey)return 0;return (a.sortKey < b.sortKey) ? g_order : -g_order;}function sortTable(tableNo, colNo, ord){var table, rows, nR, bs, i, j, temp;g_order=ord;g_colNo=colNo;table=g_tables[tableNo];rows=new Array();nR=0;bs=table.tBodies;for(i=0; i<bs.length; ++i)for(j=0; j<bs[i].rows.length; ++j){rows[nR]=bs[i].rows[j];temp=rows[nR].cells[g_colNo];if(temp) rows[nR].sortKey=temp.innerHTML;else rows[nR].sortKey="";++nR;}rows.sort(compareRows);for (i=0; i < rows.length; ++i)insAtTop(table.tBodies[0], rows[i]);}
```

## Unordered List to Ordered List

```javascript
javascript:uls=document.getElementsByTagName("ul"); for (i=uls.length-1; i>=0; --i) { oldul = uls[i]; newol = document.createElement("ol"); for(j=0;j<oldul.childNodes.length;++j) newol.appendChild(oldul.childNodes[j].cloneNode(true)); oldul.parentNode.replaceChild(newol, oldul); } void 0
```

