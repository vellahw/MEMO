# 자바스크립트 for … of (ES6)

```jsx
const count = [10, 20, 30];

// ES5
for (let i = 0; i < count.length; i++) {
  console.log(count[i]); 
}

// ES6
for (const value of count) {
  console.log(value);
}
```

컬렉션 전용 반복문임.

컬렉션 객체가 [Symbol.iterator] 속성을 가지고 있어야만 한다.

## 👀 for…in과 for..of의 차이

- for...in은 객체의 열거 가능한 **속성**을 반복
- for...of는 객체의 속성 **값을 반복**

위 말은 for in과 for of을 이용하여 문자열을 반복해보면 쉽게 와닿는다.

```jsx
const myString = "test";

for (let i in myString) {
  console.log(i); // 0, 1, 2, 3
}

for (let i of myString) {
  console.log(i); // t, e, s, t
}
```

로그 결과와 같이 for...in은 인덱스를 기록하는 반면 for...of는 문자열의 각 문자를 기록한다.

## ☝ 두 반복문 사용팁

- 항목의 인덱스 순서가 중요한 경우 for...in 사용X
    - 항목이 의도한 순서대로 제공된다는 보장이 없기 때문
- break 또는 return과 같은 문을 사용하여 루프 중 하나가 완료되기 전에 종료 할 수 있음.
- 객체의 자체 속성만 반복하려면 for...in 대신 getOwnPropertyNames() 또는 이와 유사한 것을 사용하는 것을 권장함..
    - Object.getOwnPropertyNames(): 객체의 key 값을 배열로 반환하는 메서드. 열거 가능/불가능한 속성을 모두 가져옴