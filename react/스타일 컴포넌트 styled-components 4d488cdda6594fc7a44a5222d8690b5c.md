# 스타일 컴포넌트 styled-components

사용하기 위해선 styled-components 설치가 필요.

스타일 컴포넌트를 사용할 jsx 파일 상단에 아래 코드를 입력한다.

```jsx
import styled from "styled-components";
```

## 💡 작성방법

```jsx
const FirstDiv = styled.div`
  display: flex;
`;
```

컴포넌트의 이름은 대문자로 시작해야 한다.

styled.태그명을 입력하여 웬만한 html 태그를 스타일 컴포넌트로 생성할 수 있다.

태그명 옆에 백틱 (`)을 붙이고 그 안에 적용할 스타일들을 입력해준다.

### ✔️ 스타일 상속받기

같은 파일 내에서 만들어둔 스타일 컴포넌트를 상속 받을 수 있다.

아래와 같이 입력한다. 

```jsx
const SecondDiv = styled(FirstDiv)`
   color: red; // 스타일을 추가할 경우엔 입력
`;
```

 추가해줄 스타일 속성이 없더라도 백틱은 꼭 붙여주어야 한다!

### 👀 속성 지정하기

input, button 태그 등 type 등의 속성을 지정해줘야 할 때가 있다. 그럴 땐 아래와 같이 attrs를 붙여 작성하면 된다.

```jsx
const FirstBtn = styled.button.attrs({
	type: 'submit'
})`
  display: flex;
`;
```

**attr({ })** → 중괄호 안에 위처럽 입력해주면 됨!