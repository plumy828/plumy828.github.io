---
title: "Google Analytics란?"
categories:
    - Git
tags:
    - [Git, Github, Google]
---

# 1. Google Analytics란?
[Google Analytics][googlelink]

[googlelink]: https://analytics.google.com/analytics/web/#/p344040112/reports/intelligenthome   

란 구글에서 무료로 제공하는 웹분석 서비스로 2005년 구글이 웹분석 전문업체인 어친(Urchin)사를 인수한 뒤 전세계적으로 가장 많이 사용되는 웹분석 솔루션입니다.   
방문자들의 행동 데이터를 분석하고, 마케팅의 실적이나 웹사이트의 경험을 개선할 수 있도록 도와주는 도구입니다.   
장점으로는 여러가지가 있는데   
* 일단 가격적인 면에서 무료이기 때문에 매우 유리합니다.   
* 데이터 자료를 목록, 차트, 그래프 등 다양한 형식으로 보여주기에 직관적입니다.   
* 실시간으로 데이터를 수집하기 때문에 원하는 기간의 실적을 확인하며 보고서를 만들 수 있습니다.  

이렇듯 많은 강점을 지닌 Google Analytics는 많은 사람들에게 쓰이고 있습니다.   
실제로도 2021년 1월 기준 전체웹사이트의 54.6%에서 사용되고 있다고 합니다.   

# 2. 적용하는 방법은?
뭐하는 친구인지 알았으니 이제 적용을 해야겠죠.   
일단 사이트에 접속을 합니다.   
<https://analytics.google.com>   
접속하면 먼저 가입을 하라고 뜰텐데 시키는 대로 다 해줍시다. 아주 간단하니 걱정하실 필요 없습니다.   
하고 나면 이제 회원가입을 하고 관리할 사이트를 설정해야 합니다.   

![first](./img/캡처2.PNG)   

사진대로 다 해주면   

![캡처](https://user-images.githubusercontent.com/52962027/204292601-8f3c6325-0003-4e68-b1ca-23c4ed5f35e9.PNG)   

속성이름이 뜹니다. 자신의 깃허브 repo 이름을 넣어주면   

![third](./img/캡처3.PNG)   

체크박스가 뜨는데 2개 있습니다. 내려서 꼭 체크해주면   

![fourth](./img/캡처4.PNG)   

축하합니다! 당신의 Google Analytics 계정이 생겼습니다.   
이제 관리할 사이트를 설정해줍시다.   

![fifth](./img/캡처5.PNG)   

웹 버튼을 누르면 이런 화면이 뜨는데 자신이 관리할 사이트의 주소를 적어줍시다.   

![sixth](./img/캡처6.PNG)   

그러면 이런 화면이 뜨는데 저 **측정 ID** 를 복사해줍니다.   
그러고 각자의 테마에 맞는 부분에 Google Analytics를 사용할 부분을 작성해줍시다.   
본 블로그는 `minimal-mistakes`테마를 사용중이기에 _config.yml 파일에 수정해줍니다.   

    # Analytics   
    analytics:   
        provider               : "google-gtag" # false (default), "google", "google-universal", "google-gtag", "custom"   
        google:   
            tracking_id          : "G-CBR7JH****"   
            anonymize_ip         : false # true, false (default)

이 부분에 `provider` 부분과 `tracking_id` 부분을 수정해주시면 이제   

![seventh](./img/캡처7.PNG)   

이제 작동하는 걸 볼 수 있습니다.   

# 3. 결론
이번 글에서는 Google Analytics에 대해서, 그리고 적용하는 방법에 대해 알아봤습니다. 테마에 따라 적용하는 방식이 다를 수 있지만 크게 다르지는 않을 것입니다.   
다음시간엔 더욱 다양한 기능에 대해 알아보며 이상으로 글을 마치겠습니다.