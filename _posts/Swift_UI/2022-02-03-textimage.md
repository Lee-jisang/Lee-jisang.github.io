---
title: SwiftUI 텍스트와 이미지
categories:
  - SWIFTUI
excerpt: "SwiftUI의 텍스트와 이미지에 대해서 공부해보자:)"
date: 2022-02-03 
tags:
- SwiftUI
---


# 개요


텍스트와 이미지등으로 뷰를 구성하는 방법을 알아보고 간단한 앱을 만들어보겠다.


<br />
<br />

---

# 텍스트

---

화면에 원하는 문자열을 표현하는 뷰이다.

`Text("원하는 문자열")`을 사용하면 된다.


[Text 잘 정리된 블로그](https://opendoorlife.tistory.com/12)

[Apple 공식문서](https://developer.apple.com/documentation/swiftui/text)

<br />

---

## 폰트 설정

---

함수 원형 : `func font(_ font: Font?) -> Text`


```swift
Text("hello")
  .font(.title)
  .font(.system(size: 16, weight: .light, design: .default))
```


<br />

---

## 폰트 굵기

---

함수 원형 : `func fontWeight(_ weight: Font.Weight?) -> Text`

```swift
Text("hello")
  .fontWeight(.black) 
```

<br />

---

## 글자색

---

함수 원형 : `func foregroundColor(_ color: Color?) -> Text`

```swift
Text("hello")
  .foregroundColor(.white) 
```


<br />

---

## 텍스트 주변 여백

---

```swift
Text("hello")
  .padding()
  .padding(.all, 10) // 전체
  .padding(.top, 10) // 위
  .padding(.bottom, 10) // 아래
  .padding(.leading, 10) // 왼쪽
  .padding(.trailing, 10) // 오른쪽
  .padding([.top, .bottom, .trailing], 10) // 선택
```

<br />

---

## 배경색

---

```swift
Text("hello")
  .background(Color.blue)   
```

<br />

---

## 굵게

---

```swift
Text("hello")
  .bold()  
```

<br />

---

## 기울임

---

```swift
Text("hello")
  .italic()  
```

<br />

---

## 밑줄

---

```swift
Text("hello")
  .underline()
```

<br />

---

## 취소선

---

```swift
Text("hello")
  .strikethrough()   
```

<br />

---

## 숫자 사이 간격 추가

---

```swift
Text("hello")
  .monospacedDigit()
```

<br />

---

## 텍스트 사이 간격 조절

---

텍스트 사이 간격을 조절 하는데에는 kerning과 tracking이 있다.

kerning은 글자 크기, 글자 폰트에 따라서 달라지지만 tracking은 상관없이 조절한다.

둘다 있다면 tracking이 우선사항이다.

```swift
Text("hello")
  .kerning(-3)
  .kerning(3)
  .tracking(-3)
  .tracking(3)
```


<br />

---

## 텍스트 위아래 공간 조절

---

```swift
Text("hello")
  .baselineOffset(10)
  .baselineOffset(-10)
```

<br />

---

## 텍스트 전체 대소문자 변경

---

```swift
Text("hello")
  .textCase(.lowercase)
  .textCase(.uppercase)
```


<br />

---

## 텍스트 줄수 제한

---

```swift
Text("hello")
  .lineLimit(2)   
```


<br />

---

## 텍스트 줄 사이 간격 조절

---

```swift
Text("hello")
  .lineSpacing(10) 
```

<br />

---

## 정렬 방식

---

```swift
Text("hello")
  .multilineTextAlignment(.trailing)   
```



<br />
<br />

---

# 이미지

---

에셋에 이미지가 있다면 `Image("이미지 이름")`의 명령으로 불러올 수 있다.

.frame(width: , height: )의 수식어는 크기를 변경시키는 것이 아니라 띄워주는 크기를 조절하는 것이다.

[애플 공식문서](https://developer.apple.com/documentation/swiftui/images)

<br />

---

## 이미지 크기 조절

---

func resizable(capInsets: EdgeInsets = EdgeInsets(), resizingMode: Image.ResizingMode = .stretch) -> Image

```swift
Image("SwiftUI")
  .resizable().frame(width: 50, height: 50) // 순서 바꾸면 안됨
  
Image("SwiftUI")
  .resizable(capInsets: .init(top: 0, leading: 50, bottom: 0, trailing:0))
```

<br />

---

## 이미지 크기 조절 모드

---

```swift
Image("SwiftUI")
  .resizable()
  .scaledToFit() //가로 세로중 작은값을 기준으로 비율을 유지한채로 리사이즈
  
Image("SwiftUI")
  .resizable()
  .scaledToFill()  //가로 세로중 큰값을 기준으로 비율을 유지한채로 리사이즈
```

<br />

---

## 이미지 비율 조정

---

```swift
//scaledTofit 모드 적용, 너비가 높이보다 1.6배
Image("SwiftUI")
  .resizable()
  .aspectRatio(CGSize(width: 1.6, height: 1), contentMode: .fit)

//scaledToFill 모드 적용, 너비가 높이보다 0.7배
Image("SwiftUI")
  .resizable()
  .aspectRatio(0.7, contentMode: .fill)
```


<br />

---

## 이미지 형태

---

```swift
Image("SwiftUI")
  .clipShape(Circle())  //원
  .clipShape(Rectangle().inset(by: 10) // 10 줄인 사각형
```


<br />

---

## SF Symbols

---

```swift
Image(systemName: "star.circle")
```

<br />

---

## 심볼 사이즈 조절

---

```swift
Image(systemName: "star.circle").imageScale(.small)

Image(systemName: "star.circle").font(.body)
```


<br />

---

## 심볼 굵기 조절

---

```swift
Image(systemName: "star.circle").font(Font.title.weight(.black))
```


