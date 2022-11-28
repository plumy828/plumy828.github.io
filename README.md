# GitBlog에 대한 가벼운 고찰   
본 글에선 GitBlog를 제작 및 조건에 맞게 수정하고 변경하는 과정을 서술하는 글로써
본 프로젝트를 제작하는 데에  단계를 거치며 완성했다.   

## 1. 저장소 작성 및 Jekyll을 통한 기본적인 블로그 작성   
가장 기본이 되는 `저장소`를 작성하고 GIT Bash를 이용해   

   git clone <repo_name> <path>

로 먼저 로컬 저장소에 복사해주고   
![capture1](https://user-images.githubusercontent.com/52962027/204302492-e9cad933-c57e-4a9e-bdac-6fa38db801b5.PNG)   
토큰을 생성해 패스워드란에 토큰을 입력해 git push를 한다.   
이후 GIT Bash에   

   jekyll new . --force

를 입력해 jekyll을 설치해준 뒤   

   bundle exec jekyll serve

를 입력해 jekyll을 실행하고 `http://127.0.0.1:4000/`에 접속하면   
![capture2](https://user-images.githubusercontent.com/52962027/204303972-aded378e-0792-4827-b8cd-2938feae2202.PNG)   
기본적인 블로그 화면이 나오는데 이건 의미 없고   
`_config.yml` 이 파일이 매우 중요하다. 테마를 적용하거나 블로그의 모든 기능을 추가할 때 이 파일에서 수정을 먼저 해야하기 때문이다.   
기본적으로 바꿔준 부분은   

   ```
   # Site Settings   
   title                    : "Python Sandwich"   
   title_separator          : "-"   
   name                     : "Jeong Taek"   
   description              : "An amazing website."   
   url                      : "https://plumy828.github.io"   
   repository               : "plumy828/plumy828.github.io" # GitHub username/repo-name e.g. "mmistakes/minimal-mistakes"    
   ```   

이 부분을 수정해주었다. 이름과 url, repository를 자신의 저장소에 맞게 고쳐주었다.   

## 2. Post 작성 및 테마 변경
이후 블로그에 글을 작성한다. jekyll을 install 했을 경우 `_posts` 폴더에 `Welcome to Jekyll!`이란 제목을 가진 마크다운 폴더가 보인다.   
하지만 본 프로젝트에선 테마 변경 문제와 깃허브의 사용 미숙으로 인해 repo 전체를 수 차례 갈아 엎느라 이 파일은 보이지 않는다.   
먼저 마크다운에 대해 설명하는 글을 작성해야 하는데 사용처와 함께 기본적인 문법을 서술하는 식으로 작성했다.   
글의 제목을 `=======`와 `------`로 작성하려 했는데   
`=====` 이 경우 잘 작성됐지만 `-----` 이 경우가 리스트와 겹쳐서 잘 작동하지 않아 `==`와 `--`로 작성하려는 계획은 `#`와 `##`을 사용하여 작성하였다.   
`#`으로 작성하니 문제 없이 잘 작동하는 모습이었다.   
또한 순서있는 리스트로 글의 순서를 1. 2. 2.1 로 작성하려 했는데 `===` 문제와 맞물려 1. 부분이 제대로 작동하지 못하고 2. 부분이 1. 로 치환되는 오류가 발생하였다.   
이 부분은 `#`을 사용하니 모두 해결되었다.   
전체적인 글의 순서는
* 마크다운의 사용처
+ 마크다운의 사용법
   + 제목
   + 블럭인용
   + 목록(순서있는, 순서없는)
   + 코드블럭(들여쓰기, 코드 이용)
   + 기타 사용법(하이퍼링크, 기울임체 및 볼드체)   

를 다루기로 계획했다.   
대부분의 경우 큰 문제는 없었지만 **코드블럭** 과 **기타 사용법**이 문제였다.   
코드블럭의 경우 코드블럭을 보여주는 코드블럭을 작성해야 하는데 처음 해본 방법이 그냥 들여쓰기를 쓰는 법이었고 해결한 방법이 코드블럭코드와 `<pre><code>{코드}</code></pre>`를 사용하는 법이었다.   
코드블럭코드는 처음엔 들여쓰기를 사용했지만 제대로 인식하지 못하는 오류가 발생해서 해결방안을 찾다가 `<pre><code>{코드}</code></pre>` 안에 설명하려는 코드를 넣었더니 성공했다.   
`<pre><code>{코드}</code></pre>`를 설명할 땐 반대로 적용해 코드블럭코드 안에 설명하려는 코드를 넣어서 성공했다.   
그 다음 `깃허브에선 코드블럭코드 사용시점에 언어를 넣어서 강조할 수 있다`   
이 부분을 설명할 때는 의외로 오류가 발생하지 않아 깔끔하게 작성할 수 있었다.   
하이퍼링크를 설명할 때도 오류가 있었는데 `//사용한 코드` 부분에서 내가 이걸 썼다고 보여줘야 하는데 코드의 결과가 나오고 아래 결과 코드는 오히려 보여주려는 코드로 나와 서로 반대로 나오고 말았다.   
이 경우 코드블럭코드를 사용해 해결했다.   
그리고 사소한 문제였는데 `기울임 및 볼드체`를 설명할 때   
결과도 안나오고 줄바꿈도 안되있었는데 `   ` 띄어쓰기 3번과 코드블럭코드를 이용하니 해결되었다.   
Markdown에 관련한 첫번째 글을 제작하며 **코드블럭코드**와 **띄어쓰기 3번**의 덕을 정말 똑똑히 봤다. 만약 코드블럭코드와 띄어쓰기 3번이 없었더라면 지금 작성하고 있는 글을 포함해 나머지 2개의 글을 작성하지 못했을 것이다.   

테마는 총 2번 변경하였다.   
기본 -> minimal-mistakes -> scriptor -> minimal-mistakes   
처음 테마를 변경했을 땐 fork하거나 다운로드 한게 아닌 더미 정보만 가져왔기 때문에 생긴건 그럴싸해도 정작 글이라든지 댓글과 같은 기능을 추가할 때 아무런 도움이 되지 않았다.   
그래서 아직 미숙했던 난 테마 문제인가 싶어 다른 테마인 **scriptor**로 테마를 변경하게 되었고 이번엔 테마를 다운로드해 내 repo에 옮겨넣었다.   
이번엔 수업 때 배운 `_layouts` 폴더라든지 `_includes` 폴더가 생겨 이번엔 되겠다 싶었지만 글 작성자의 Gitblog에 대한 지식 및 theme 변경의 미숙으로 인해 다시 한번 무리하게 **minimal-mistakes**로 변경하게 되었고 코드가 꼬인 나머지 결국 repo를 한번 초기화하게 되었다.   
초기화를 한 뒤 이번엔 강의 슬라이드에 나온대로 처음 상태에서 **minimal-mistakes**를 다운받아 작동이 되는지 확인하고 처음과 같은 상태로 `_config.yml`파일을 수정하고 **minimal_mistakes** 제작자가 올린 사이트에서 테마 적용 방법이나 댓글 기능 추가, Google analytics 적용을 순차적으로 추가 및 수정했다.   
중간중간 사소한 문제가 있어 add, commit, push를 미친듯이 반복했다.   

## 3. 댓글 기능 추가 및 Google analytics 적용
댓글 기능을 추가하기 위해 처음엔 수업 때 배운대로 **disqus**를 먼저 이용했다.   
수업 때는 disqus에 가입해 `_config.yml`파일에   
```
comment:   
   provier:    "disqus"   
   disqus:   
      shortname:   "plumy828-github-io"

defaults:   
   values:   
      comments: true
```   
를 적도록 알려줬었는데 강의자 분의 테마가 나와 다른 부분도 있었고 왜인지 모르겠지만 계속 적용이 안되는 오류가 발생하여 결국 **utterance**를 사용하기로 했다.   
**utterance**는 **disqus**보다 오히려 편했다. Github 앱으로 되어있어 설치만 하면 됐고 추가해야할 부분도 `_config.yml`에   
```
comments:   
   provider       : "utterances"
```
정도만 추가하면 됐었다. 그리고 친구가 알려주기로 disqus는 생각보다 오류가 잘나 utterance를 쓰는 것이 더 효율적이라고 했다.   
하지만 그럼에도 불구하고 **utterance**에서도 오류가 나 다시 한번 repo를 갈아엎고 적용했더니 작동했다.   
제작자의 사이트에 `불필요한 파일 제거`라는 항목이 있어서 그거대로 따라했더니 코드 의존성이 꼬인 것 같았다.   
댓글 기능을 성공적으로 추가하고 시험 댓글을 단 뒤 **Google analytics**를 적용하기로 했다.   
생각보다 **Google analytics**는 더더욱 간단했다.   
그냥 `_config.yml`코드에   
```
# Analytics   
analytics:   
  provider               : "google-gtag" # false (default), "google", "google-universal", "google-gtag", "custom"   
  google:   
    tracking_id          : "G-CBR7JH1CSC"   
    anonymize_ip         : false # true, false (default)
```   
정도만 추가하면 됐다.   
Google analytics를 들어가니 자동으로 구글 계정을 선택하라는 안내가 나왔고 시키는대로 한뒤 본 블로그의 **Google Analytics란?** 글에 나온대로 했더니 간단하게 작동했다.   
이 과정에서 주목할 부분은 `tracking_id`였는데 간단하게 스트림과 웹사이트 주소를 적어주면 자동으로 주어지는 토큰과 같은 번호였는데 크게 어려운 부분이 없었다.   

## 4. favicon 추가하기
일단 `favicon`을 처음 들어본 작성자에겐 검색이 우선이었다.   
**favicon**이란 **favorite icon**의 줄임말로 웹사이트 또는 웹 페이지를 대표하기 위해 웹브라우저에서 사용되는 16 * 16 픽셀의 작은 이미지라고 한다.   
깃허브에서   
![capture3](https://user-images.githubusercontent.com/52962027/204323445-68c0c8de-cc9a-4113-9726-8a2e88fa64aa.PNG)   
이것과 같은 뜻이다.   
이런 부분에선 특별한 favicon을 설정하고 싶어 theme 제작자가   
`./includes/head/custom.html`에서 알려준 사이트   
<https://realfavicongenerator.net/>
를 먼저 가보았다. 하지만 여긴 로컬로 다운받은 이미지를 favicon으로 전환시켜주는 사이트라 일단은 이미지를 찾기로 했다.   
<https://www.flaticon.com/>이라는 많은 사람들이 추천해주는 favicon 이미지 검색 사이트가 있길래 이곳을 이용해 내 테마와 맞는 **contrast**와 맞는 이미지를 검색했다.   
음양무늬가 있길래 내 테마와 어울릴거라 생각해 다운받고 위의 사이트에서 전환했다.   
전환하니 이런 화면으로 바뀌면서   
![capture4](https://user-images.githubusercontent.com/52962027/204324986-47ff4599-3e3e-45f3-ab65-f065dd871b20.PNG)   
지시사항이 나왔다.   
시키는 대로 붙여넣기 하고 push 후 실행해봤지만 적용되지 않았다.   
이유가 있을까 싶어 제작자가 답변해준 글을 찾아보았다. 마침 나와 같은 문제를 겪는 사람이 질문을 했고 거기서 해답을 찾아냈다.   
위의 코드는 보편적인 경우고 나 같은 경우는 따로 폴더를 만들어 그 안에 이미지를 저장했기에   
```
<link rel="apple-touch-icon" sizes="180x180" href="/assets/logo.ico/apple-touch-icon.png">   
<link rel="icon" type="image/png" sizes="32x32" href="/assets/logo.ico/favicon-32x32.png">   
<link rel="icon" type="image/png" sizes="16x16" href="/assets/logo.ico/favicon-16x16.png">
```   
위처럼 `href="`부분을 내가 해당하는 경로로 바꿔줘야만 이미지를 찾을 수 있던 것이었다.   
실제로 이 부분을 수정하고나니 적용되었다.   

## 5. 글을 마치며
생각보다 빨리 끝날줄 알았던 Gitblog 과제는 새벽까지 시간을 써야할 정도로 시간이 오래걸렸으며 원래도 오래걸리는 과제에 작성자의 미숙한 판단과 부족한 지식으로 인해 몇배는 더 걸린듯 하다.   
하지만 이번 프로젝트를 통해 Markdown의 문법을 정말 확실히 익혔으며 Gitblog를 포함한 Git과 Github의 사용법을 다시한번 확실히 할 수 있었던 프로젝트였다.   
내 개인 역량을 시험 및 향상시킬수 있었던 좋은 순간이었으며 피곤과 비례해 내 지식이 늘어난 것에 대한 알 수 없는 감정을 느끼며 글을 마친다.