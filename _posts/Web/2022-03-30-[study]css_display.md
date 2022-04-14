---
title: "CSS Display"
excerpt: "How to use CSS Display properly"
excerpt_separator: "<!--more-->"
categories:
  - Web
tags:
  - CSS
  - flex
  - block
  - inline
  - inline-block
last_modified_at: 2022-03-30T20:40:00
---

<!--more-->

<br>

## CSS Display

#### CSS의 Display란?

- 웹 페이지에서 element들이 어떻게 보여지고 다른 element와 어떻게 상호작용할지를 정하는 배치 속성
- 박스 유형을 결정 짓는다.
- 요소들의 위치를 결정짓는 속성인 position과 float에 비해 우선도가 떨어진다.

#### CSS Display 종류

- block
  <br>![CSS Display Block](/assets/img/css_display_block.jpg)
  - 가로 한 줄을 다 차지
  - 모든 margin, padding 요소가 적용 가능하다.
  - ex) div, p, h1...
- inline
  <br>![CSS Display Inline](/assets/img/css_display_inline.jpg)
  - 줄 바꿈 없이 나란히 배치된다.
  - width, height 속성 지정 불가
  - margin과 padding의 top, bottom 간격 지정 불가
  - ex) span, a...
- inline-block
  <br>![CSS Display Inline_Block](/assets/img/css_display_inlineblock.jpg)
  - inline과 block의 특성을 같이 가지고 있다.
  - 전후 줄 바꿈 없이 나란히 배치된다. <== inline
  - width, height 속성 지정 가능 <== block
  - margin, padding 상하 간격 지정이 가능하다. <== block
  - ex) button, select...
- flex
  <br>![CSS Display Flex](/assets/img/css_display_flex.jpg)
  - 메인 축을 기반으로 정렬을 진행한다.
  - flex를 선언한 부모 요소는 flex-container로, 자식 요소들은 flex-item들로 역할한다.

#### Flex

<br>![CSS Display Flex](/assets/img/css_flex.png)

- Flex Container 속성

  - display: flex container를 정의
  - flex-flow: flex-direction과 flex-wrap의 단축 속성
  - flex-direction: flex 속성의 정렬 기준, 즉 주축(main-axis)을 설정
  - flex-wrap: flex item들의 여러 줄 묶음(줄 바꿈) 설정
  - justify-content: 주 축의 정렬 방법 설정
  - align-content: 교차 축(cross-axis)의 정렬 방법 설정
  - align-items: 교차 축에서 items의 정렬 방법 설정

- Flex Items 속성
  - order: flex item의 순서 설정
  - flex: flex-grow, flex-shrink, flex-basis의 단축 속성
  - flex-grow: flex item의 증가 너비 비율 설정
  - flex-shrink: flex item의 감소 너비 비율 설정
  - flex-basis: flex item의 기본 너비 설정
  - align-self: 교차 축에서 item의 정렬 방법 설정
