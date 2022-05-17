# Document and website structure
시멘틱 태그를 사용하여 문서 구조를 만드는 방법과 간단한 웹사이트 구조를 만드는 방법을 배운다.

## 문서의 기본 섹션
- header : 일반적으로 큰 제목과 로고 등이 있는 큰 띠.한 웹페이지에서 주요 정보가 있는 곳.
- navigation bar : 홈 페이지로부터 다른 페이지로 넘어가도록 구성뙤있다.
- main content : 웹 페이지에서 가장 독특한 컨텐츠를 포함하고 있는 중심의 큰 부분.
- sidebar : 주변의 정보, 링크, 인용 부호, 광고 등.  일반적으로 이는 메인 컨텐츠에 무엇이 포함되어 있느냐에 따라 다르다.
- footer : 페이지 바닥의 줄로 일반적으로 작은 정보, 저작권 정보, 또는 연락처 등을 포함하고 있다. 보통 중요하지 않거나, 부차적인 정보를 표현. 가끔 SEO목적으로 사용되는데, 인기 컨텐츠 바로가기 링크를 제공한다.

## 컨텐츠 구조화를 위한 HTML
HTML 코드에서 기능에 따라 콘텐츠 섹션을 마크업할 수 있다.
콘텐츠 섹션을 나타내는 요소를 명확하게 사용할 수 있으며 스크린리더와 같은 보조 기술에서 이러한 요소를 인식하고
"기본 탐색 찾기" 또는 "주요 콘텐츠 찾기" 같은 ***올바른 작업에 올바른 요소 구조와 의미 체게를 사용하지 않으면 여러 가지 결과가 발생한다.*** 

이러한 시맨틱 마크업을 구현하기 위해 HTML은 이러한 섹션을 나타내는 데 사용할 수 있는 전용 태그를 제공한다.
- 헤더 : ```<header>```
- 탐색 모음 : ```<nav>```
- 주요 콘텐츠 : ```<main>```로 표시되는 다양한 콘텐츠의 하위 섹션이 있다. ```<article> <section> <div>```
- 사이드바 : ```<aside>``` main태그 내부에 배치하는 경우가 많다.
- 바닥글 : ```<footer>```

## HTML 레이아웃의 세부사항
- ```<main>``` : 페이지당 한 번만 ```<main>```을 사용하고 중첩되지 않아야 이상적이다.
- ```<article>``` : 페이지에서 자체적으로 의미가 있는 관련 콘텐츠 블록을 묶습니다.
- ```<section>``` : ```<article>```과 유사하지만, 하나의 단일 기능을 구성하는 페이지의 단일 부분(ex: 미니 맵 또는 기사 헤드라인 및 요약 세트)을 그룹화
- ```<aside>``` : 주요 내용과 직접적으로 관련되지는 않지만 간접적으로 관련 추가 정보를 제공할 수 있는 내용을 포함
- ```<header>``` : 소개 콘텐츠 그룹을 나타낸다. 웹페이지의 전역 헤더를 정의한다.
- ```<nav>``` : 페에지의 기본 탐색 기능을 포함한다. 보조 링크 등은 탐색에 포함되지 않는다.
- ```<footer>``` : 페이지의 최종 콘텐츠 그룹을 나타낸다.

### 의미 없는 래퍼
때로는 요소 세트를 함께 그룹화하여 일부 CSS 또는 JavaScript를 사용하여 단일 엔티티로 모든 요소에 영향을 미치고 싶을 수도 있다.

이러한 경우 HTML은 ```<div>```, ```<span>```요소를 제공한다. class 속성과 함께 사용하여 쉽게 타게팅할 수 있도록 일종의 레이블을 제공한다.

```<span>``` 내용을 감싸는 더 나은 의미 체계 텍스트 요소가 생각나지 않거나 특정 의미를 추가하고 싶지 않은 경우에만 사용해야 하는 비의미적 인라인 요소이다.

```<div>```는 블록 수준의 의미 없는 요소이다. 더 나은 의미의 블록 요소가 생각나지 않거나 특정 의미를 추가하고 싶지 않은 경우에만 사용해야 한다.

### 줄 바꿈 및 가로 규칙
- ```<br>``` : 단락에 줄 바꿈을 만든다. 우편 주소나 시와 같이 일련의 고정된 짧은 줄을 원하는 상황에서 단단한 구조를 강제하는 유일한 방법이다.

```html
<p>There once was a girl called Nell<br>
Who loved to write HTML<br>
But her structure was bad, her semantics were sad<br>
and her markup didn't read very well.</p>
```

- ```<hr>``` : 텍스트의 주제 변경을 나타내는 문서에 수평선을 만든다.

```html
<p>Ron was backed into a corner by the marauding netherbeasts. Scared, but determined to protect his friends, he raised his wand and prepared to do battle, hoping that his distress call had made it through.</p>
<hr>
<p>Meanwhile, Harry was sitting at home, staring at his royalty statement and pondering when the next spin off series would come out, when an enchanted distress letter flew through his window and landed in his lap. He read it hasily, and lept to his feet; "better get back to work then", he mused.</p>
```

## 웹사이트 계획하기
간단한 웹페이지의 콘텐츠를 계획했다면 다음 논리적 단계는 전체 웹사이트에 어떤 콘텐츠를 넣고 싶은지, 어떤 페이지가 필요한지, 어떻게 정렬하고 서로 연결해야 하는지 알아내는 것이다.

이를 정보 아키텍처라고 한다.

1. 구성 요소의 페이지에 기본적으로 포지셔닝
2. 각 페이지의 구조를 그리고, 블록의 기능을 구상.
3. 웹사이트에 포함시키길 원하는 컨텐츠를 brainstorm해라.
4. 이 모든 컨텐츠들을 그룹화 해 다른 페이지 어떤 부분들이 함께할 수 있을지 생각할 수 있다.
5. 대략적인 사이트맵을 그리시오.


