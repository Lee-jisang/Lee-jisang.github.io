---
title: Java Script
categories: 
  - Language
excerpt: Java Script의 모든 것
date: 2022-04-06
tags:
- JavaScript
---



# JavaScript 개념
---

HTML은 웹 사이트에서 화면에 표시되는 정보를 약속 한 것이며, CSS는 구체적으로 어떤 스타일로 요소가 표시 되는지를 정하는 규격이라고 할 수 있습니다.
위 둘은 정적인 것만 할 수 있는 언어인데요, 대표적으로 사용자의 반응에 따라 유동적으로 화면과 내용이 바뀌는 일은 처리할 수 없다는 것입니다.

JavaScript는 웹페이지를 동적으로 만들어주는 언어로, 객체 기반의 스크립트 프로그래밍 언어입니다.
단순히 규격을 나타내는 HTML과 CSS와 달리, 변수와 함수 등이 존재하는 프로그래밍 언어이며, 현재도 활발한 발전이 이루어지고 있습니다.

Java와는 거의 관계가 없습니다. (이름만 따왔으며, 설계 근본부터 다름)
브라우저(Chrome, Internet Explorer 등) 안에서 실행되는 클라이언트 언어로, 엔드유저 단에서 동작합니다.

JavaScript를 줄여서 js라고 하며 파일 확장자 또한 .js를 사용합니다.

<br />


# 사용법
---

CSS와 비슷하게 HTML문서 내에 기술하거나 별도의 파일로 분리하여 사용합니다.

```html
<!-- HTML 내에 기술 -->
<html>
<head>
	<script type="text/javascript">
		document.write('Hello World!');
	</script>
</head>
<body>
</body>
</html>
```

```html
<!-- 외부 파일에서 불러오기 -->
<head>
	<script type="text/javascript" src="JS파일위치.js"></script>
</head>
```

<br />


# 스크립트 언어
---

JavaScript는 스크립트 언어이자 인터프리터 방식이 사용되어, 컴파일 과정이 필요 없습니다.

브라우저에서 즉시 해석되어 실행되는데, 한 곳에서 만든 엔진을 사용하지 않기 때문에
브라우저마다 완전 동일한게 동작하다고 하기 어렵습니다.

개발 속도가 빠르고 문법이 간단하지만, 복잡한 프로그램을 만들기는 어렵다는 특징이 있습니다.

<br />

# 동적타입 언어
---

자바스크립트에에서는 개발자가 변수의 타입을 지정해주지 않습니다.
정확히 말하면 변수의 값에 따라 인터프리터가 알아서 변수의 타입을 파악하고 값을 저장합니다.

```c
int a = 10;
char b = 'K';

int main() {
	return 2;
}
```

C나 Java같은 기존 정적타입 언어에선 위처럼 변수나 함수를 선언했다면
JavaScript에서는 아래처럼 var이나 function이라는 키워드를 사용하며, 타입을 명시하지 않습니다.

```javascript
var a = 10;
var b = 'K';

function main() {
	return 2;
}
```

