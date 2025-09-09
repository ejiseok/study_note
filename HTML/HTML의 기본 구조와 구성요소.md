# HTML의 기본 구조와 구성요소

## HTML이란?

HTML(HyperText Markup Language)은 웹 페이지가 어떤 의미와 구조를 가지고 있는지 브라우저로 하여금 알 수 있도록 하는 [마크업 언어](https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EC%97%85_%EC%96%B8%EC%96%B4)이다. HTML은 요소(elements)로 구성되어 있으며 태그(tags)를 이용해 페이지 내의 컨텐츠들을 감싸고 의미를 부여한다. 예를 들어, 아래 내용은 그냥 평범한 문장이지만

```html
My cat is very grumpy
```

아래처럼 `<p>` 태그로 감싸주면 해당 문장을 문단(paragraph) 요소로 명시할 수 있다.

```html
<p>My cat is very grumpy</p>
```

| HTML 요소는 대소문자 구분을 하지 않는다. 위에서 예로 든 `<p>` 태그 또한 `<p>`와 `<P>` 어느 쪽을 사용해도 문제 없이 사용 가능하나, 보통은 가독성과 기타 호환성 때문에 소문자로 통일하여 작성한다.

## HTML 요소(Element)의 구조

![HTML 요소 구조](https://developer.mozilla.org/ko/docs/Learn_web_development/Core/Structuring_content/Basic_HTML_syntax/grumpy-cat-small.png)

HTML 요소(Element)의 구성요소는 아래와 같다.

- 여는 태그(Opening Tag): `<p>`처럼 요소의 이름과 열고 닫는 꺽쇠로 구성되어 있다. 이는 해당 요소의 효과가 적용되기 시작하는 위치를 나타낸다.
- 닫는 태그(Closing Tag): `</p>`처럼 여는 태그와 비슷하지만 요소 이름 앞에 슬래시(`/`)가 붙는다. 해당하는 요소의 끝 부분을 나타내며, 일부 예외를 제외하고 닫는 태그를 명시하지 않으면 의도하지 않은 결과가 나타날 수 있다.
- 내용(Content): 요소의 내용에 해당하며, 여는 태그와 닫는 태그 사이에 위치한다.
- 요소(Element): 여는 태그와 닫는 태그, 내용을 한꺼번에 묶어 요소(Element)라고 한다.

### 중첩된 요소(Nesting Elements)

요소 안에는 또 다른 요소가 포함될 수 있으며, 이 때 해당 요소를 중첩되었다고 말한다. 예를 들어, "My cat is very grumpy"라는 문장에 "very"를 강조하기 위해서 글자에 굵은 효과를 줄 수 있는 `<strong>` 요소를 중첩하여 사용 가능하다.

```html
<p>My cat is <strong>very</strong> grumpy</p>
```

또한 요소를 중첩시키기 위해서는 반드시 안쪽에 위치하는 중첩된 태그가 먼저 닫혀야한다(위 예시에서는 `<strong>` 태그가 먼저 닫힌 다음 `<p>` 태그가 닫혀야 함).

```html
<!-- 잘못된 문장! -->
<p>My cat is <strong>very grumpy</p></strong>
```

### 블록 레벨 요소(Block-level elements)와 인라인 요소(Inline elements)

HTML에는 크게 두 가지 요소(Element)가 있다. 블록 레벨 요소(Block-level elements)와 인라인 요소(Inline elements)다.

- 블록 레벨 요소(Block-level elements)는 웹페이지 상에 블록(block)을 만들어 다른 요소들과 다른 아예 새로운 줄(Line)에 표현한다.
- 인라인 요소(Inline elements)는 새로운 줄을 만들지는 않는다. 여러개의 인라인 요소를 연속으로 작성하면 그것들은 한 단락 안에 위치하게 된다.

```html
<em>first</em>
<em>second</em>
<em>third</em>

<p>fourth</p>
<p>fifth</p>
<p>sixth</p>
```

위 코드에서 `<em>`은 인라인 요소, `<p>`는 블록 레벨 요소이다. 앞선 설명에 따라 `first`, `second`, `third`는 같은 줄에, `fourth`, `fifth`, `sixth`는 각각 다른 줄에 표시된다.

![블록 레벨 요소와 인라인 요소](https://github-production-user-asset-6210df.s3.amazonaws.com/38320277/487153161-da7bd797-43c3-4bb2-a42f-baf3e520e6bb.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250909%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250909T074853Z&X-Amz-Expires=300&X-Amz-Signature=308cbb90aa91bae1ec99feb76343a58b5550933b7546ec8e87ad2c5a20a4fa54&X-Amz-SignedHeaders=host)

### 빈 요소(Empty elements)

HTML의 모든 요소가 여는 태그, 닫는 태그, 내용의 구조를 가지는 것은 아니다. 닫는 태그 없이 단일 태그(Single tag)를 사용하는 요소도 있다. `<img>` 요소는 웹페이지에 이미지를 삽입하기 위한 요소이다.

```html
<img
  src="https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png"
/>
```

![파이어폭스 로고](https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png)

## 속성(Attributes)

요소는 아래 이미지와 같이 속성을 가질 수 있다.

![HTML 요소의 속성](https://developer.mozilla.org/ko/docs/Learn_web_development/Core/Structuring_content/Basic_HTML_syntax/grumpy-cat-attribute-small.png)

속성은 실제로 화면에 표시되지는 않지만 해당하는 요소에 추가적인 정보를 담을 수 있다.

또한 속성을 사용할 때는 아래 내용을 지켜야 한다.

1. 요소의 이름 바로 다음에 오는 속성은 사이에 공백이 하나 있어야 하며, 속성이 하나 이상일 경우에는 각 속성 사이에 공백이 있어야 한다.
2. 속성 이름 다음에는 등호(`=`)가 붙는다.
3. 속성 값은 따옴표로 감싸야 한다.

### 참과 거짓 속성(Boolean attributes)

HTML에는 값이 없는 속성도 있다. 이를 불리언(Boolean) 속성이라고 한다. 예를 들어, `disabled` 라는 속성이 있는데, 이를 입력 요소에 할당하면 사용자가 데이터를 입력할 수 없도록 비활성화 할 수 있다.

```html
<input type="text" disabled /> <input type="text" />
```

![활성화 된 입력 요소와 비활성화 된 입력 요소](https://github-production-user-asset-6210df.s3.amazonaws.com/38320277/487160581-6aa9243e-ac43-4ab5-9681-c93a5dc8c9ee.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20250909%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20250909T080055Z&X-Amz-Expires=300&X-Amz-Signature=89dcbd51b9c51c6bfe83491d5b5844cba25bca3844744bf66065219e819556f8&X-Amz-SignedHeaders=host)
