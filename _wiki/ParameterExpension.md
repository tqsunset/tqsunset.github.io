---
layout  : wiki
title   : Parameter Expansion(매개변수 확장)
summary : 
date    : 2021-09-02 23:43:53 +0900
updated : 2021-09-03 00:36:27 +0900
tags    : bash, shell, unix 
toc     : true
public  : true
parent  : [[UNIX]]
latex   : false
---
* TOC
{:toc}

# 

## 매개변수 확장이란

어떤 변수 foo=cde가 있다고 하자. 'abcde' 스트링을 만들기 위해 foo를다음과 같이 사용할 수 있다.
```
$ foo=cde

$ echo "ab$foo"
abcde

# 'ab$foo'와 같이 따옴표만 사용했을 땐 작동하지 않음
```
이와 같이 기존의 스트링 변수를 간단히 조작할 수 있다.

## abdcefg?

그렇다면 'abcdefg' 스트링을 만들기 위해서는 어떻게 해야하는가?
```
$ echo "ab$foofg"	# foofg라는 변수의 값은 null이므로 ab만 출력된다.
ab

$ echo "ab${foo}fg"	# $가 뒤에 붙은 {}에만 적용되므로 나머지 스트링과 구분이 가능하다.
abcdefg
```

## String length
변수 앞에 #를 붙이면 해당 변수가 가진 문자 수를 표시한다.
```
$ foo="Hello world"
$ echo ${#foo}
11
```

## Substring removal 

