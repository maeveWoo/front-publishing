# Advanced text formatting

## Description lists
이 리스트의 목적은 용어 및 정의, 질문 및 답변과 같은 일련의 항목 및 관련 설명을 표시하는 것이다.

Description lists는 다른 타입의 리스트와 다르게 ```<dl>```를 사용한다. 용어, 질문과 같은 상위 항목은 ```<dt>```(description term) 요소를 사용하고,
정의, 답변과 같은 하위 항목은 ```<dd>``` (description definition) 요소를 사용한다.

```html
<dl>
  <dt>soliloquy</dt>
  <dd>In drama, where a character speaks to themselves, representing their inner thoughts or feelings and in the process relaying them to the audience (but not to other characters.)</dd>
  <dt>monologue</dt>
  <dd>In drama, where a character speaks their thoughts out loud to share them with the audience and any other characters present.</dd>
  <dt>aside</dt>
  <dd>In drama, where a character shares a comment only with the audience for humorous or dramatic effect. This is usually a feeling, thought or piece of additional background information.</dd>
</dl>
```
브라우저에서 제공하는 기본 스타일에 의해서 정의, 답변과 같은 하위 항목에 대해서 들여쓰기가 적용된다.

## 인용구
HTML에는 인용구 표시에 사용할 수 있는 요소가 존재한다. 해당 요소는 블록 또는 인라인 요소인지에 따라서 다르게 표시된다.

### Blockquotes
블록 레벨 컨텐츠의 섹션(문단, 여러 단락, 리스트등)이 인용된 경우, 이를 나타내는 ```<blockquote>```요소로 감싼다.

그리고 ```cite``` 속성에 출처를 표기한다.

```html
<blockquote cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote">
    <p>The <strong>HTML <code>&lt;blockquote&gt;</code> Element</strong> (or <em>HTML Block
        Quotation Element</em>) indicates that the enclosed text is an extended quotation.</p>
</blockquote>
```

### Inline quotations
인라인 인용구는 ```<q>``` 요소를 사용한다는 점만 제외하면 블럭 인용구와 동일하게 동작한다.

```html
<p>The quote element — <code>&lt;q&gt;</code> — is <q cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q">intended
for short quotations that don't require paragraph breaks.</q></p>
```

### Citations
```cite```요소의 컨텐츠는 유용하게 보이지만 브라우저, 스크린 리더 등은 이를 이용해서 할 수 있는 것이 많지 않다.

페이지에서 인용 출처를 화면에 나타나게 하고 싶다면 ```<cite>``` 요소를 사용하는 것이 좋다.
이는 이름 그대로 출처를 포함하기 위해서 사용된다. ```<cite>``` 요소 안에 있는 출처에 대한 링크를 연결할 수 있다.

```html
<p>According to the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote">
<cite>MDN blockquote page</cite></a>:
</p>

<blockquote cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote">
  <p>The <strong>HTML <code>&lt;blockquote&gt;</code> Element</strong> (or <em>HTML Block
  Quotation Element</em>) indicates that the enclosed text is an extended quotation.</p>
</blockquote>

<p>The quote element — <code>&lt;q&gt;</code> — is <q cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q">intended
for short quotations that don't require paragraph breaks.</q> -- <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q">
<cite>MDN q page</cite></a>.</p>
```

## 약어
```<abbr>```요소를 종종 볼 수 있다. 이는 머리 글자 또는 약어를 나타내는데 사용된다.

title 속성을 통해 원래의 용어를 나타낼 수 있다. 

```html
<p>We use <abbr title="Hypertext Markup Language">HTML</abbr> to structure our web documents.</p>

<p>I think <abbr title="Reverend">Rev.</abbr> Green did it in the kitchen with the chainsaw.</p>
```
용어의 전체 뜻은 마우스를 올려 놓으면 툴팁에 표시된다.

> :warning: <abbr>과 동일하게 사용할 수 있는 <acronym>가 존재한다. 이는 사용중지 되었으며 브라우저에서도 호환되지 않는 경우가 있다.

## 연락처 세부 사앙 표시
```<address>```태그를 이용해서 연락처 세부 정보를 표시할 수 있다.

```html
<address>
    <p>Chris Mills, Manchester, The Grim North, UK</p>
</address>
```
기억해야 할 것은 ```<address>```요소는 HTML 문서를 작성한 사람의 연락처 정보를 표시하기 위해서 사용되어야 한다는 것이다.

## 위첨자와 아래 첨자
종종 날짜, 화학 공식 및 수학 방정식과 같은 항목을 표시 할 때 올바른 의미를 갖도록 위첨자 아래 첨자를 사용해야 할 수도 있다.

```<sup>```, ```<sub>``` 요소들을 사용할 수 있다.

```html
<p>My birthday is on the 25<sup>th</sup> of May 2001.</p>
<p>Caffeine's chemical formula is C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>.</p>
<p>If x<sup>2</sup> is 9, x must equal 3 or -3.</p>
```

## 컴퓨터 코드를 나타내기
HTML을 이용해 컴퓨터 코드를 나타낼 때 아래와 같ㅇ은 요소들을 사용할 수 있다.
- <code>: 일반적인 컴퓨터 코드를 표시합니다.
- <pre>: 공백(일반적으로 코드 블록)을 유지하기 위해 사용합니다. 택스트 내에서 들여 쓰기 또는 초과 공백을 사용하면 브라우저가 이를 무시하고 렌더링 된 페이지에 공백을 표시하지 않습니다. 그러나 <pre></pre> 태그로 텍스트를 감싸면 공백이 텍스트 편집기에서 보는 것과 동일하게 렌더링 됩니다.
- <var>: 변수이름을 특별하게 표시합니다.
- <kbd>: 컴퓨터에 입력 된 키보드 (및 기타 유형) 입력을 표시합니다.
- <samp>: 컴퓨터 프로그램의 출력을 표시합니다.

```html
<pre><code>var para = document.querySelector('p');

para.onclick = function() {
  alert('Owww, stop poking me!');
}</code></pre>

<p>You shouldn't use presentational elements like <code>&lt;font&gt;</code> and <code>&lt;center&gt;</code>.</p>

<p>In the above JavaScript example, <var>para</var> represents a paragraph element.</p>


<p>Select all the text with <kbd>Ctrl</kbd>/<kbd>Cmd</kbd> + <kbd>A</kbd>.</p>

<pre>$ <kbd>ping mozilla.org</kbd>
<samp>PING mozilla.org (63.245.215.20): 56 data bytes
64 bytes from 63.245.215.20: icmp_seq=0 ttl=40 time=158.233 ms</samp></pre>
```

## 시간과 날짜 표시
HTML은 기계가 읽을 수 있는 형식(machine-readable)으로 시간과 날짜를 표시하기 위한 ```<time>```요소를 제공한다.

```html
<time datetime="2016-01-20">20 January 2016</time>
```
이는 왜 유용할까? 시간을 표현하는 방법은 너무 다양하다

- 20 January 2016
- 20th January 2016
- Jan 20 2016
- 20/06/16
- 06/20/16
- The 20th of next month
- 20e Janvier 2016
- 2016年1月20日
- And so on

이런 다양한 형식은 컴퓨터가 쉽게 인식할 수 없다. ```<time>```요소를 사용하면 기계가 읽을 수 있는 명확한 시간/날짜를 첨부 할 수 있다.

아래 예제는 기계 판독 가능한 날짜를 제공하지만 사용 가능한 다른 많은 옵션들이 존재한다.

```html
<!-- Standard simple date -->
<time datetime="2016-01-20">20 January 2016</time>
<!-- Just year and month -->
<time datetime="2016-01">January 2016</time>
<!-- Just month and day -->
<time datetime="01-20">20 January</time>
<!-- Just time, hours and minutes -->
<time datetime="19:30">19:30</time>
<!-- You can do seconds and milliseconds too! -->
<time datetime="19:30:01.856">19:30:01.856</time>
<!-- Date and time -->
<time datetime="2016-01-20T19:30">7.30pm, 20 January 2016</time>
<!-- Date and time with timezone offset-->
<time datetime="2016-01-20T19:30+01:00">7.30pm, 20 January 2016 is 8.30pm in France</time>
<!-- Calling out a specific week number-->
<time datetime="2016-W04">The fourth week of 2016</time>
```
