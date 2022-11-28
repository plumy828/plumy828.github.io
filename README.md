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

   # Site Settings
   title                    : "Python Sandwich"
   title_separator          : "-"
   name                     : "Jeong Taek"
   description              : "An amazing website."
   url                      : "https://plumy828.github.io" 
   repository               : "plumy828/plumy828.github.io" # GitHub username/repo-name e.g. "mmistakes/minimal-mistakes"
   # breadcrumbs            : false # true, false (default)

이 부분을 수정해주었다. 이름과 url, repository를 자신의 저장소에 맞게 고쳐주었다.   

## 2. Post 작성 및 테마 변경
이후 블로그에 글을 작성한다. jekyll을 install 했을 경우 `_posts` 폴더에 `Welcome to Jekyll!`이란 제목을 가진 마크다운 폴더가 보인다.   
하지만 본 프로젝트에선 테마 변경 문제와 깃허브의 사용 미숙으로 인해 repo 전체를 수 차례 갈아 엎느라 이 파일은 보이지 않는다.   
먼저 마크다운에 대해 설명하는 글을 작성해야 하는데 사용처와 함께 기본적인 문법을 서술하는 식으로 작성했다.   
글의 제목을 `=======`와 `------`로 작성하려 했는데   
`=====` 이 경우 잘 작성됐지만 `-----` 이 경우가 리스트와 겹쳐서 잘 작동하지 않아 `==`와 `--`로 작성하려는 계획은 `#`와 `##`을 사용하여 작성하였다.   
`#`으로 작성하니 문제 없이 잘 작동하는 모습이었다.   
또한 순서있는 리스트로 글의 순서를 1. 2. 2.1 로 작성히려 했는데 `===` 문제와 맞물려 1. 부분이 제대로 작동하지 못하고 2. 부분이 1. 로 치환되는 오류가 발생하였다.   
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
하이퍼링크를 설명할 때도 오류가 있었는데 코