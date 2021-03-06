# HTML text fundamentals
HTML의 주요 작업 중 하나는 브라우저가 텍스트를 올바르게 표시 할 수 있도록 텍스트 구조와 의미(시멘틱이라고도 함)를 제공하는 것이다.

## 기본적인 것: 제목과 단락
대부분의 구조화 된 텍스트는 기사, 신문, 대학 교과서, 잡지 등 무엇을 읽든지 간에 제목과 단락으로 구성된다.

구조화된 컨텐츠는 읽는 경험을 더 쉽고 즐겁게 만들어준다.

heeading 요소는 총 6개가 있다. h1~h2 태그. 각 요소는 문서에서 다른 수준의 내용을 나타낸다.

### 구조화된 계층을 구현하기
구조화된 계층이 타당해 보이는 한 연관된 요소들이 정확히 무엇을 나타내는지는 당신에게 달렸다.
다만 그러한 구조들을 만들 때 다음 몇 가지의 관례만 기억하면 된다.

- 가급적 페이지 당 하나의 ```<h1>``` 만 사용해야 한다. ```<h1>```은 최상위에 있는 표제이며 나머지 다른 표제들은 계층적으로 이것 밑에 위치한다.
- 각 표제들을 계층적으로 올바른 순서로 사용해야 함을 명심. ```<h3>```을 하위 표제로 사용하고 그 다음 ```<h2>```를 아래의 하위 표제로 사용하지 마세요.
- 6개의 Heading 을 사용할 수 있지만 꼭 필요한 것이 아니라면 한 페이지에 3개 이상을 사용하지 않도롣 해라. 많은 목차 레벨을 가진 문서는 다루기 힘들고 탐색하기 어렵다. 이러한 상황에서는 가능하다면 컨텐츠를 여러 페이지로 나누는 것이 바람직하다.

### 왜 우리는 구조가 필요할까?
- 웹 페이지를 보는 유저는 필요한 컨텐츠를 빠르게 훑어보는 경향이 있고 자주 heading만 읽기도 한다. 몇 초 안에 필요한 어떤 것도 찾지 못하면 그들은 실망하고 다른 곳으로 갈 수도 있다.
- 검색 엔진들은 당신의 페이지 내 heading을 페이지 검색 순위에 영향을 주는 중요한 키워드로 고려해 indexing 한다. heading이 없다면, 당신의 페이지는 검색 엔진 최적화에 관해서는 형편없게 된다.
- 심각한 시각 장애인들은 종종 웹페이지를 읽지 못한다. 대신 그들은 screen reader라고 불리는 소프트웨어를 사용해 웹페이지를 듣는다. 그것은 heading을 읽어줌으로서 문서의 개요를 제공하며 사용자들이 필요로하는 정보를 빠르게 찾을 수 있도록 한다.
- 컨텐츠를 CSS로 꾸미거나, JS로 흥미로운 일을 하게 하기 위해서, 당신은 관련 컨텐츠를 감싸는 요소가 필요하다.

그러므로 우리는 컨텐츠를 구조적인 markup에 적용시켜야 한다.

### 우리는 왜 Semantic을 필요로 할까?
Semantic(의미를 담은, 의미론적인)은 우리 주변 어디에서나 사용된다. 우리는 정확한 요소를 사용하고 있는지, 우리의 컨텐츠에 정확한 의미, 기능, 모습을 담았는지 확실히 해야한다.

비슷한 맥락에서, 우리는 정확한 요소를 사용하고 있는지, 으리의 컨텐츠에 정확한 의미, 기능, 모습을 담았는지 확실히 해야 한다.
이 맥락에서 ```<h1>```요소  또한 텍스트에 "내 페이지 최상위 heading"의 역할로 감싸는 semantic 요소이다.

```html
<h1>This is a top level heading</h1>
```

기본적으로, 브라우저는 이에 큰 사이즈의 폰트응 적용해 heading처럼 보이게 할 것이다. 더 중요하게, 이는 의미론적인 가치는 다양한 방식으로 사용될 것이다.
예를 들어 검색엔진이나 screen reader들에서 말이다.

반면에, 어떤 요소도 최상위 heading처럼 보이게 할 수 있다.
```html
<span style="font-size: 32px; margin: 21px 0;">Is this a top level heading?</span>
```
이것은 ```<span>```요소이다. 의미가 없다. 이것을 CSS를 더해 최상위 heading처럼 보이게 했지만, 이것이 semantic 가치는 없다. 작업에 관계있는 HTML요소를 사용하는 것이 좋다.

## Lists
너무 많이 쓰이는 리스트. 우리는 3가지 고려할 사항이 있다.

### Unordered (순서 없음)
정렬되지 않은 목록은 항목의 순서가 중요하지 않은 항목 목록을 표시하는 데 사용된다.

순서 없는 리스트를 정렬하기 위해 ```<ul>``` element를 이용해 감싸준다.

### Ordered (순서 있음)
순서 있는 리스트는 항목의 순서가 중요한 목록이다.

```<ol>```태그로 감싸는것을 제외하고는 마크업 구조는 순서가 없는 리스트와 동일

### 리스트 내부의 리스트 (Nesting lists)
```html
<ol>
  <li>Remove the skin from the garlic, and chop coarsely.</li>
  <li>Remove all the seeds and stalk from the pepper, and chop coarsely.</li>
  <li>Add all the ingredients into a food processor.</li>
  <li>Process all the ingredients into a paste.
    <ul>
      <li>If you want a coarse "chunky" hummus, process it for a short time.</li>
      <li>If you want a smooth hummus, process it for a longer time.</li>
    </ul>
  </li>
</ol>
```

## 중요와 강조
가장 일반적인 몇 가지 요소를 살펴보기로 한다.

### 중요 (Emphasis)
우리는 말을 하면서 특정 단어를  강세를 두고 발음하는 방법으로 의미를 다르게 표현한다.
마찬가지로, 글에서는 단어에 강세를 두기 위해 이탤릭체로 표현하는 경향이 있다.

HTML에서는 이러한 경우를 표시하기 위해 ```<em>```(emphasis)요소를 사용한다.
문서를 더 흥미롭게 읽게 될 뿐만 아니라, 화면판독기에 인식되면 다른 톤의 목소리로 표현된다. 
브라우저에서 기본적으로 이탤릭체로 스타일을 지정하지만,  단지 이탤릭체로 스타일링하기 위해 이 태그를 사용하는 것은 지양한다.
스타일링을 위해서는 ```<span>```요소에 약간의 CSS를 더하거나 ```<i>```요소를 사용할 수 있다.

### 강조 (Strong importance)
중요한 단어를 강조하기 위해 강세를 두고 말하거나 글자를 두껍게 표현한다.

HTML에서 이러한 경우를 표시하기 위해 ```<strong>```(strong importance)요소를 사용한다.
문서를 더 유용하게 만드는 것뿐만 아니라, 화면판독기에 인식되면 다른 톤의 목소리로 표현된다.
마찬가지로 단지 스타일링하기 위해서 사용하는 것은 지양한다. 스타일링을 위해서는 ```<span>```요소를 사용하거나 ```<b>```요소를 사용할 수 있다.

### Italic, bold, underline...
```<b>```, ```<i>```, ```<u>```이 요소들은 CSS가 형편없이 지원되거나 완전히 지원되지 않는 경우에 이탤릭체 또는 밑줄 등을 표현할 수 있도록 고안되었다.
의미론적이 아닌 표현에만 영향을 주는 이와 같은 요소들은 현재적 요소로 알려져 있으며, 더 이상 사용되어서는 안된다.

HTML5에서는 ```<b>```, ```<i>```, ```<u>```를 조금 혼란스럽긴 하지만 새로운 의미론적 역할로 재정립했다.
