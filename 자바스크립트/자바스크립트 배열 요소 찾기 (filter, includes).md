# 자바스크립트 배열 요소 찾기 (filter, includes)

## 1. filter()

```jsx
array.filter(조건 함수)
```

- 조건에 해당하는 값을 **배열**로 반환한다.
- 빈 요소에 대해서는 함수를 실행하지 않는다
- 조건에 해당하는 값이 없다면 빈 배열을 반환한다.

### 👉 예시

```jsx
const arr = [1, 2, 3, 4, 5]

const checkValue = (num) => {
    return num >= 3
}

const result = arr.filter(checkValue)
console.log(result) // [3, 4, 5]
```

## 2. includes()

```jsx
array.includes(조건)
```

- 배열에 조건에 맞는 값이 있으면 `true`가 반환됨
- 조건에 맞는 값이 없다면 `false` 가 반환됨
- 조건문의 문자열은 대소문자를 구분함

### 👉 예시

```jsx
const fruits = ["Banana", "Orange", "Apple", "Mango"];
        
if(fruits.includes("Mango")){ // true
    console.log("망고를 찾았다!") // log 찍힘
}
```

```jsx
const fruits = ["Banana", "Orange", "Apple", "Mango"];

if(fruits.includes("mango")){ // false
    console.log("망고를 찾았다!")
} else {
    console.log("대소문자를 구분함") // 이 문자열이 찍힘
}
```