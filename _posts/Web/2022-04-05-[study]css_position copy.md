---
title: "CSS POSITION & FLOAT"
excerpt: "How to use CSS Position properly(feat. Float)"
excerpt_separator: "<!--more-->"
categories:
  - Web
tags:
  - CSS
  - static
  - absolute
  - fixed
  - relative
  - inherit
  - float
last_modified_at: 2022-04-05T18:40:00
---

<!--more-->

<br>

## CSS Position

#### CSS의 Position이란?

- 웹 페이지에서 문서 상의 요소를 배치하는 방법을 지정하는 속성
- 좌표를 지정하기 위해 left, right, top, bottom 속성과 함께 사용한다.
- position을 absolute나 fixed로 설정할 시 가로 크기가 100%인 block 요소들의 특징이 사라지게 된다.

#### CSS Position 종류

- static
  <br>![CSS Position Static](/assets/img/css_position_static.jpg)
  - position 속성값 중 default 값
  - 다른 태그와의 관계가 그대로 적용되며, 다른 속성을 통해 위치를 임의로 바꾸는 것이 가능하다.
- absolute
  <br>![CSS Position Absolute](/assets/img/css_position_absolute.jpg)
  - 요소를 일반적인 문서 흐름에서 제거하고 절대적인 좌표를 통해 위치를 지정한다.
  - 초기 컨테이닝 블록(Containing Block)을 기준으로 한다.
    **position:absolute;일 때 컨테이닝 블록: position 속성값이 static이 아닌 가장 가까운 조상 엘리먼트**
  - 절대 좌표의 값은 left, right, top, bottom을 통해 지정할 수 있다.
- relative
  <br>![CSS Position Relative](/assets/img/css_position_relative.jpg)
  - 자기 자신의 본래 위치를 기준으로 상대적 위치를 계산하여 현 위치를 지정한다.
  - 상대적 위치값은 left, right, top, bottom을 통해 지정할 수 있다.
  - 자식 엘리먼트의 크기에 따라 부모 엘리먼트의 크기가 자동으로 변하지만, 엘리먼트의 위치에 따라 변하지는 않는다.
  - 뒤에 연속하여 오는 엘리먼트들에게 영향을 주지 않는다.
- fixed
  - 요소를 일반적인 문서 흐름에서 제거하고, 문서의 가장 좌측 상단을 기준으로 스크롤에 관계 없는 고정 위치를 잡는다.
  - 실질적으로 위치 기준은 뷰포트(viewport, 현재 화면에 보여지고 있는 다각형의 영역)나 페이지 영역이다.
  - 절대 좌표의 값은 left, right, top, bottom을 통해 지정할 수 있다.
- sticky
  <br>![CSS Position Sticky](/assets/img/css_position_sticky.jpg)
  - 스크롤 위치에 따라 스크롤이 임계점을 넘어가면 fixed로 동작시킨다.
- inherit
  - 부모 태그의 속성을 그대로 상속받는다.
- initial
  - 요소의 속성값을 초기화 하는 것.

## Float이란?

- float은 display의 flexbox를 사용하기 이전에 많이 사용하던 레이아웃 방식이다.
- 해당하는 엘리먼트를 문서의 일반적 흐름에서 빠져나오게 한 뒤, 해당 엘리먼트 주변의 텍스트 및 인라인 요소가 엘리먼트 주변에 어떻게 배치될지를 결정한다.
- float에 left를 하는 경우
  <br>![CSS Float Left](/assets/img/css_float_left.jpg)
- float에 right를 하는 경우
  <br>![CSS Float Right](/assets/img/css_float_right.jpg)
