# [Webhacking.kr] old-14

:writing_hand: [h0meb0dy](mailto:h0meb0dysj@gmail.com)

## Analysis

![image](https://user-images.githubusercontent.com/104156058/179828480-c9f15b87-e46a-459a-a942-44fcb1139a06.png)

페이지의 소스를 보면 자바스크립트 코드가 있다.

```javascript
function ck(){
  var ul=document.URL;
  ul=ul.indexOf(".kr");
  ul=ul*30;
  if(ul==pw.input_pwd.value) { location.href="?"+ul*pw.input_pwd.value; }
  else { alert("Wrong"); }
}
```

`ul == pw.input_pwd.value`가 되도록 하면 문제가 풀린다.

## Solve

![image](https://user-images.githubusercontent.com/104156058/179957996-6ca14b2e-f5c4-486f-a6ed-6e5013ed2824.png)

![image](https://user-images.githubusercontent.com/104156058/179958164-4b7d1318-1861-4165-a366-40b74c5d539c.png)

540을 넣고 check를 누르면 문제가 풀린다.