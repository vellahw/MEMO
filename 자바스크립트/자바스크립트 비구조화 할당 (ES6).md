# 자바스크립트 비구조화 할당 (ES6)

ES6 문법의 대표적인 예로는 let과 const, 화살표 함수, 템플릿 리터럴 등이 있는 것을 알고 사용하고 있었다.

그런데 ES6 문법인지도 모른채 자연스럽게 사용하고 있던 문법들이 있어서, 정리할겸 기록해본다.

첫 번째로 비구조화 할당~!

## 비구조화 할당

배열이나 객체의 속성을 해체하여 그 값을 개별 변수에 담을 수 있는 표현식

```jsx
// ES5
const testObject = {
    name: "vellahw",
    date: "230929",
    content: "hello!"
}

let name = testObject.name
let date = testObject.date
let content = testObject.content

console.log(name) // vellahw
console.log(date) // 230929
console.log(content) // hello!
```

ES5에서 위처럼 객체.속성명으로 쓰던 표현식을

```jsx
// ES6
const testObject = {
    name: "vellahw",
    date: "230929",
    content: "hello!"
}

let { name, date, content} =  testObject

console.log(name) // vellahw
console.log(date) // 230929
console.log(content) // hello!
```

ES6에선 위와 같이 표현할 수 있다.

```jsx
const [first, ...etc] = [1, 2, 3];
console.log(first); // 1
console.log(etc); // [2, 3] (배열)
```

위와 같은 할당 또한 가능하다.

변수 first만 1이라는 값 하나만 할당되고, 변수 etc엔 그 이후의 값들이 배열로 할당된다.