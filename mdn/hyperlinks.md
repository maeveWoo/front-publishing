# 하이퍼링크 만들기
## 링크의 구조
```<a>```태그를 사용!. ```href```속성(target으로 알려진)은 사이트의 주소가 포함된 링크를 보여준다. 

```html
<p>I'm creating a link to
    <a href="https://www.mozilla.org/en-US/">the Mozilla homepage</a>.
</p>
```

### title 속성에 부가적인 정보를 더하기
```title``` 속성은 해당 페이지에 어떤 종류의 정보가 포함되어 있는지 또는 알아야할 사항과 같은 링크에 대한 보충할만한 유용한 정보를 포함하기 위한 것을 나타낼때 사용한다.

```html
<p>I'm creating a link to
    <a href="https://www.mozilla.org/en-US/"
       title="The best place to find more information about Mozilla's
          mission and how to contribute">the Mozilla homepage</a>.
</p>
```
해당 링크에 마우스는 오버랬을때에 툴팁에 대한 기능도 제공해줄 수 있다.

## URL과 path에 대한 기본 지침 
URL(Uniform Resource Locator)은 단순히 무언가가 웹상의 어디에 위치하는지 결정하는 하나의 텍스트 문자열이다.
(ex: https://www.mozilla.org/en-US/)

URL은 파일들을 찾기위해 path를 이용한다. path는 파일이 파일 시스템 어디에 있는지 구체적으로 명시한다. 

### Document fragments (문서 조각)
문서 상단이 아닌 HTML 문서 내부의 특정 부분(Document fragments(문서 조각)에 링크 할 수 있다.)에 링크 할 수 있다.

먼저 링크를 시키고 싶은 태그에 ```id``` 속성을 넣어 주어야한다.
```html
<h2 id="Mailing_address">Mailing address</h2>
```

특정 ID에 연결하려면 URL 끝에 해시/파운드 기호를 포함하면 된다.

```html
<p>Want to write us a letter? Use our <a href="contacts.html#Mailing_address">mailing address</a>.</p>
```

Document fragments(문서 조각)를 단독으로 사용하여 동일한 문서의 다른 부분에 연결할 수 있다.

```html
<p>The <a href="#Mailing_address">company mailing address</a> can be found at the bottom of this page.</p>
```

### 절대 URL과 상대 URL
절대 URL : 웹에서 정의된 상대적인 위치를 가리킨다. protocol 과 domain name 포함. 

절대 URL은 어디에 사용되든 항상 같은 장소를 가리킨다.

상대 URL : link하고 있는 파일로부터 상대적인 위치를 가리킨다. 

상대 URL은 파일의 실제 위치가 어디냐에 따라 다른 장소를 가리킬 것이다.

## Link 실습하기
### Link 명을 명확하게
- 스크린리더 사용자들은 링크에서 페이지 링크를 타고, 컨텍스트에서 벗어난 링크를 읽는 것을 좋아한다.
- 검색 엔진은 링크 텍스트를 사용하여 대상 파일을 인덱싱하므로 링크 텍스트에 키워드를 포함시켜 링크되는 내용을 효과적으로 설명하는 것이 좋다
- 시각적 독자들은 한 마디 한 마디를 읽기보다는 페이지를 훑어보고, 링크는 페이지에서 눈에 띄게 보여질 것이다.

다른 팁들
- 링크를 텍스트의 일부로 URL을 작성하지 마세요  - URL은 보기 흉하며, 스크린 리더가 URL을 읽어낼 때 이상하게 들린다.
- 링크 텍스트에 "link"니 "links to"라고 쓰지마라 - 이는 단지 소음이다. 
- 링크 라벨은 가능한 짧게 유지하다
- 동일한 텍스트의 여러 복사본이 서로 다른 위치에 연결되는 것을 최소화해라.

### 가능하면 상대 링크 사용하기
절대 링크를 사용하는 것이 좋은 생각이라 할 수 있다. 그러나 동일한 웹 사이트 내의 다른 위치를 연결할 때 가능한 한 상대 링크를 사용해야 한다.
- 상대 링크가  절대 링크보다 훨씬 짧기 때문에 코드를 읽는 것이 훨씬 쉽다.
- 상대 URL을 이용하는 것이 더 효율적이다. 절대 URL을 사용할 때, 브라우저는 DNS를 타고 서버 요청을 받는다. 상대 URL은 브라우저가 요청되는 파일과 같은 서버를 찾아볼 ㅅ뿐이다.  
이는 절대 URL을 사용하면 브라우저가 계속해서 추가 작업을 수행하도록 만들 수 있으며, 이는 브라우저의 성능이 저하된다는 것을 의미한다.

### 비 HTML 리소스 연결 시 - 명확한 표식 남기기
PDF나 워드 문서와 같이 다운로드되거나 스트리밍되거나(비디오나 오디오와 같은) 다른 예상하지 못한 효과(팝업 창을 열거나 플래시 동영상을 로드)에 연결할 때는 명확한 표현을 추가하여 혼란을 줄 수 있어야 한다.

예를 들어
- 대역폭이 낮은 경우 링크를 클릭하면 멀티 메가바이트 다운로드가 예기치 않게 시작된다.
- 플래시 플레이어를 설치하지 않은 경우 링크를 클릭한 다음 플래시가 필요한 페이지로 이동한다.

사용할 수 있는 텍스트의 종류를 보려면 아래 예를 보자
```html
<p><a href="http://www.example.com/large-report.pdf">
  Download the sales report (PDF, 10MB)
</a></p>

<p><a href="http://www.example.com/video-stream/">
  Watch the video (stream opens in separate tab, HD quality)
</a></p>

<p><a href="http://www.example.com/car-game">
  Play the car game (requires Flash)
</a></p>
```

### 다운로드 연결 시 download attribute 사용
브라우저에서 열지 않고 다운로드할 리소스에 연결하는 경우 다운로드 속성을 사용하여 기본 저장 파일 이름을 제공할 수 있다.

Firefox 39의 Windows버전에 대한 다운로드 링크가 있는 예

```html
<a href="https://download.mozilla.org/?product=firefox-39.0-SSL&os=win&lang=en-US"
   download="firefox-39-installer.exe">
    Download Firefox 39 for Windows
</a>
```
오예!

## 이메일 링크
클릭했을 때 리소스나 페이지에 연결하지 않고 새 발신 전자 메일 메시지를 여는 링크나 단추를 만들 수 있다.

```<a>```태그안에 ```mailto``` URL 스키마를 사용하여 구현할 수 있다.

가장 기본적이고 일반적으로 사용되는 형태의 ```mailto``` 링크는 단순히 대상 수신인의 이메일 주소를 표시한다.

에메일 주소는 선택사항이다. 이를 생략하면, 주소가 지정되지 않은 사용자의 메일 클라이언트에 의해 새로운 발신 이메일 창이 열린다.

### 세부 사항 지정하기
이메일 주소 외에도 다른 정보를 제공할 수 있다. 실제로 표준 메일 헤더 필드는 사용자가 제공하는 ```mailto``` URL에 추가할 수 있다.

이들 중 가장 일반적으로 사용되는 것은 "subject", "cc", "body"이다.

예제
```html
<a href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&amp;subject=The%20subject%20of%20the%20email &amp;body=The%20body%20of%20the%20email">
  Send mail with cc, bcc, subject and body
</a>
```
> 각 필드의 값은 URL로 인코딩되어야 한다.(즉, 출력되지 않은 문자 및 percent-escaped). 또한 "mailto:" URL의 각 필드를 구분하는 "&"의 사용에 유의하라. 이는 표준 URL 쿼리 표기법이다.

```mailto``` URL 샘플들이다.
- mailto:
- mailto:nowhere@mozilla.org
- mailto:nowhere@mozilla.org,nobody@mozilla.org
- mailto:nowhere@mozilla.org?cc=nobody@mozilla.org
- mailto:nowhere@mozilla.org?cc=nobody@mozilla.org&subject=This%20is%20the%20subject


