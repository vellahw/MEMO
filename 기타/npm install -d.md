# npm install -d

### 개발 단계에서만 필요한 패키지 설치하기

 -d 플래그를 붙여 devDependencies 목록에 설치할 수 있다.

```jsx
npm install -d (패키지명)
```

### dependencies와 devDependencies의 차이

1. dependencies
    1. 실제 코드에도 포함되며 앱 구동을 위해 필요한 패키지
2. devDependencies
    1. 실제 코드에 포함되지 않으며 ‘개발 단계에서만’ 필요한 패키지

### devDependencies는 설치 안 할래요

```jsx
npm install -production
```

npm install 명령어를 실행하면 package.json에 기록된 모든 패키지들이 설치된다.

devDependencies에 설치된 패키지들은 개발 단계에서만 필요한 패키지들이니 설치할 필요가 없기 때문에, -production 플래그를 붙여주면 됨.