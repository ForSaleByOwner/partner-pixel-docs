# partner-pixel-docs
Partner Pixel Documentation

```javascript
<script>
 
// place this code in the <head> tag
(function(p,i,x,e,l,s) {
  p[x] = function() {
    e = [].splice.call(arguments,0);
    l=i.createElement('script');
    l.src='//widget-log.forsalebyowner.com/api/pp/'+e[0]+'?e='+e[1]+'&'+e.slice(2).join('&')+'&'+p.location.search.substr(1);
    s=i.getElementsByTagName('body')[0]; s.appendChild(l);s.removeChild(l);
  }
})(window, document, 'fsbop');
 
// Then somewhere in the <body> of the page...
 
// Track that the user simply visited the page
// Replace '[PARTNER CODE]' with the actual partner code. You can get that from the dev team.
// Example: fsbop('98NzeQ4YB1e', 'landed');
fsbop('[PARTNER CODE]', 'landed');
 
// Work with the partner to add other events that make sense. The name of the event can be whatever makes sense to you.
// Example, track when the user submits the form on a landing page
fsbop('[PARTNER CODE]', 'form-submitted');
 
</script>
```
