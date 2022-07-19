# [Webhacking.kr] old-01

:writing_hand: [h0meb0dy](mailto:h0meb0dysj@gmail.com)

## Analysis

![image](https://user-images.githubusercontent.com/104156058/179827669-38112a63-6486-4c38-8c57-889513057652.png)

```php+HTML
<?php
  include "../../config.php";
  if($_GET['view-source'] == 1){ view_source(); }
  if(!$_COOKIE['user_lv']){
    SetCookie("user_lv","1",time()+86400*30,"/challenge/web-01/");
    echo("<meta http-equiv=refresh content=0>");
  }
?>
<html>
<head>
<title>Challenge 1</title>
</head>
<body bgcolor=black>
<center>
<br><br><br><br><br>
<font color=white>
---------------------<br>
<?php
  if(!is_numeric($_COOKIE['user_lv'])) $_COOKIE['user_lv']=1;
  if($_COOKIE['user_lv']>=4) $_COOKIE['user_lv']=1;
  if($_COOKIE['user_lv']>3) solve(1);
  echo "<br>level : {$_COOKIE['user_lv']}";
?>
<br>
<a href=./?view-source=1>view-source</a>
</body>
</html>
```

`user_lv` 쿠키의 값이 1로 설정되어 있는데, 이 쿠키의 값이 3보다 크고 4보다 작으면 문제가 풀린다.

## Solve

쿠키의 값을 3.5로 설정하고 새로고침하면 된다.

![image](https://user-images.githubusercontent.com/104156058/179828055-e1148469-6f2d-4151-8c23-e3cb3727a4ed.png)