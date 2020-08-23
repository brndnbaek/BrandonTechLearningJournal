---
title: Shopify 새로운 테마 만들기
excerpt: Shopify 기존에 사용중인 테마에서 원하는 방식으로 고치는거 포기하고 완전히 처음부터 하나 하나 만들어 보기로 결심.
featured_image: ''
image_caption: ''
tags:
- blog
- shopify

---
선배형의 shopify 웹스토어 수정작업을 도우면서 웹디자인을 시작하게 되었습니다. html/css 시작하는데 아주 기초적인것만 알고 있는 왕초보가 이미 런칭한 웹스토어를 그것도 shopify 구성에 맞게 돌아가고 있는것에 손을 보는게 쉬운 작업은 아니였습니다.

그나마 파일들 보면서 대충 어떤식으로 돌아가는지 알게 되었고 원하는 부분을 고치고 싶을때 무한검색작업을 해가며 이것저것 바꿔보고 고치고 하면서 조금씩 배우게 되었습니다.

지금 런칭한 웹스토어의 문제점을 꼽아본다면 로딩이 너무 오래 걸립니다. 특히 데스크탑 환경에서 들어가게 되면 처음 화면이 자리 잡는데 대략 10초 가량은 걸리고 있습니다. 구글크롬 데브툴에 있는 lighthouse로 평가를 받아본 결과 이미지 파일 크기와 불필요한 js, css들이 많이 있다고 나오고 있습니다.

이미지 파일 크기는 기존에 어느정도 정리를 했는데 메가메뉴 만드는 과정에서 기존 프로덕트와 연결된 이미지를 불러오게끔 했는데 이 메가메뉴 프로그램에 lazyloading 기능이 없다보니 렌더링할 이미지 크기와 상관없이 샤피파이 cdn에서 오리지날 원본을 불러오고 있다보니 어처구니 없이 썸네일로 보여질 이미지를 1메가크기의 이미지를 사용하는 일이 생기고 있습니다. (애초에 1메가 크기의 이미지 파일을 넣지 말아야 하는데 이게 왜 들어갔는지.. 흐음.)

아무튼 시간 나는데로 뭔가 새로운거 배우는데로 ( 모를땐 보이지 않던것이 배우고 나서는 살짝 눈에 들어오는 부분이 생기기 시작하네요) 하나씩 손보고 있는데 이게 코드 스프리딩 개념인건지 무슨 레이아웃 하나 손보려고 하면 그거랑 연계된 파일들이 꼬리에 꼬리를 물듯 서로 관련되어 있다보니 너무 복잡하게 느껴집니다. 그리고 처음에 테마를 만든 코더가 불친절하게도 아무런 서식이나 코맨트 없이 독자적인 방법으로 써놓고 이것저것 이어붙이는 방식으로 만들어놔서 스타일 하나 건드리는것도 만만치가 않습니다.

가장 황당한것은 처음에 로딩되는 css 파일중에 부트스트랩3 / 기본base css/ 그리고 샤피파이로부터 불러오는 알수 없는 css 파일. 이거 3가지가 크롬데브툴에서 확인해보면 전체 파일크기가 거진 2메가 정도 되는데 사용량은 5%도 안되는것으로 확인됩니다. 결국 각 파일에 스타일 문장 10개 미만되는것을 사용하겠다고 cdn에서 불러오는 방법으로 작업을 해놨네요.