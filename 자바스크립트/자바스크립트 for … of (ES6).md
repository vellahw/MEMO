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