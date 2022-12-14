---
title: "마크다운이란?"
categories:
    - Git
tags:
    - [Git, Github, Markdown]
---

# 1. 마크다운이란?
Markdown은 텍스트 기반의 마크업언어로 특수기호와 문자를 이용한 매우 간단한
문법을 이용해 웹에서 보다 빠르고 직관적으로 컨텐츠를 작성할 수 있다.
마크다운을 사용하는 웹서비스로는   
+ Github
+ jekyll
+ Discord
+ reddit
+ 네이버 밴드 

등이 있다. 본 수업에서 학부생들은 Markdown문법을 이용해 Gitblog를 제작하는 건 물론 Markdown의 문법 사용을 익혀 후에 있을 사용을 도모한다.   

# 2. 마크다운 사용법
## 2.1. 헤더(Headers)
큰제목을 쓰려면 제목 밑줄에 ```=```를 글 길이만큼 작성합니다.

    이것은 제목입니다
    ================   

이것은 제목입니다
================

작은 제목을 쓰려면 제목 밑줄에 ```-```를 글 길이만큼 작성합니다.

    이것은 부제목입니다
    ------------------

이것은 부제목입니다
------------------   

또한 ```#```을 통해서도 제목을 작성할 수 있습니다.   

    # This is a H1
    ## This is a H2
    ### This is a H3
    #### This is a H4
    ##### This is a H5
    ###### This is a H6   

# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6   
####### This is a H7(지원하지 않습니다)   

## 2.2. BlockQuote 
```>``` 꺽쇠문자를 이용합니다.   

    > 첫번째 블럭인용
    >    > 두번째 블럭인용
    >    >    > 세번째 블럭인용   

> 첫번째 블럭인용
>    > 두번째 블럭인용
>    >    > 세번째 블럭인용   

블럭인용 문장에서 다른 마크다운 문법을 사용할 수 있습니다.   

## 2.3. 목록
순서있는 목록은 숫자와 점을 직관적으로 사용합니다.   

    1. 첫번째
    2. 두번째
    3. 세번째   

1. 첫번째
2. 두번째
3. 세번째   

또한 번호와 상관없이 순차적으로 적용됩니다.   

    2. 첫번째
    3. 두번째
    1. 세번째   

1. 첫번째
2. 두번째
3. 세번째   

순서 없는 목록을 쓰기 위해선 ```*, +, -```를 이용합니다.   

    * 아침
        * 점심
            * 저녁
    + 아침
        + 점심
            + 저녁
    - 아침
        - 점심
            - 저녁   

* 아침
    * 점심
        * 저녁
+ 아침
    + 점심
        + 저녁
- 아침
    - 점심
        - 저녁   

섞어서 사용할 수도 있습니다.   

    * 하나
        + 둘
            - 셋
                - 넷

* 하나
    + 둘
        - 셋
            - 넷

## 2.4 코드블럭
4개의 띄어쓰기 또는 한개의 탭으로 들여쓰기를 하면 세로줄이 생기며 변환됩니다.
들여쓰지 않은 행을 쓰기 전까지 적용됩니다.   

### 2.4.1 들여쓰기   

    평범한 글 쓰기   

        코드 작성하기   

    코드 작성 마치기   

실제로 적용하면 이렇게 됩니다.

평범한 글 쓰기

    코드 작성하기   

코드 작성 마치기   

### 2.4.2 코드블럭   
다음과 같이 이용할 수 있습니다.   

* `<pre><code>[코드]</code></pre>`코드작성

    ```
    <pre>   
    <code>   
    print("Hello, World!")
    </code>   
    </pre>   
    ```

<pre>
<code>
print("Hello, World!")
</code>
</pre>

* 코드블럭코드("\```") 사용시   

<pre>
<code>
```    
print("Hello, World!")   
```
</code>
</pre>


```
print("Hello, World!")
```   

또한 깃헙에서는 "`````" 사용시점에 언어를 선언해 문법강조가 가능합니다.   

    ```java
    public class Test {
        public static void main(String[] args) {
            print("Hello, World!");
        }
    }
    ```

```java
public class Test {
    public static void main(String[] args) {
        print("Hello, World!");
    }
}
```   

## 2.5. 기타 사용법  
* 이외에도 링크를 달거나   
```
[Title][id]   
[id]: URL "Optional Title here"   

// 사용한 코드   
Link: [Naver][naverlink]

[naverlink]: https://naver.com "Go Naver"
```   

Link: [Naver][naverlink]

[naverlink]: https://naver.com "Go Naver"   

> 하지만 이런식으로 다는것이 보통의 경우 편하다

    * 사이트 링크: <http://site.com/>
    * 이메일: address@email.com

* 사이트 링크: <http://naver.com/>
* 이메일: address@email.com

* 강조문구를 사용할 수 있다.   

```
*기울임체*   
_기울임체_   
**볼드체**   
__볼드체__   
~~취소선~~   
```   

*기울임체*   
_기울임체_   
**볼드체**   
__볼드체__   
~~취소선~~   

+ 중복으로 사용할 수 있다.   

```
***기울임볼드체***   
~~***기울임볼드체 취소선***~~
```   

***기울임볼드체***   
~~***기울임볼드체 취소선***~~   

이 외에도 다양한 문법으로 활용할 수 있는 방법이 많지만 본 글에선 수업에서 주로 취급한 것들만 다루며 이상으로 글을 마치겠습니다.