# Partner Pixel Documentation
 
 * [Manual Integration](#manual-integration) 
 * [Google Tag Manager Integration](#google-tag-manager-integration) 
 
A widget partner can opt into our pixel program which will allow us to track conversions. The partner adds a snippet of code to the affected landing page and from that pixel we will collect details about that user through one or more events. At least a visited event is tracked but we may work with the partner to include additional event tracking that makes sense to the business reporting.

To implement this feature, a partner needs to add the following code you the landing page they want to track:

## Manual Integration

### Place this code in the `<head>` tag

```javascript
<script>
(function(p,i,x,e,l,s) {
  p[x] = function() {
    e = [].splice.call(arguments,0);l=i.createElement('script');l.async=true;l.src='//widget-log.forsalebyowner.com/api/pp/'+e[0]+'?e='+e[1]+'&'+e.slice(2).join('&')+'&'+p.location.search.substr(1);s=i.getElementsByTagName('body')[0]; s.appendChild(l);s.removeChild(l);
  }
})(window, document, 'fsbop');
</script>
```

### Then somewhere in the `<body>` of the page...

#### Track a visit

```javascript
<script>
// Track that the user simply visited the page
fsbop('[PARTNER CODE]', 'visited');
</script>
```

#### Track a conversion

```javascript
<script>
// To track conversions, you need to trigger this code when your users convert.
// For instance, when a user hits a submit button on a form, you can call this code.
fsbop('[PARTNER CODE]', 'form-submitted');
</script>
```

Note, you need to replace `[PARTNER CODE]` with the actual partner code that was provided to you.

## Google Tag Manager Integration

**THIS SECTION IS NOT YET COMPLETE**

You may integrate with your GTM instance by adding the following code as a tag:

```javascript
<script>
(function(p,i,x,e,l,s) {
  p[x] = function() {
    e = [].splice.call(arguments,0);l=i.createElement('script');l.async=true;l.src='//widget-log.forsalebyowner.com/api/pp/'+e[0]+'?e='+e[1]+'&'+e.slice(2).join('&')+'&'+p.location.search.substr(1);s=i.getElementsByTagName('body')[0]; s.appendChild(l);s.removeChild(l);
  }
})(window, document, 'fsbop');
</script>

<script>
// Track that the user simply visited the page
fsbop('[PARTNER CODE]','vistied','url='+encodeURIComponent({{Page URL}}),'referrer='+encodeURIComponent({{Referrer}})
);
</script>
```
