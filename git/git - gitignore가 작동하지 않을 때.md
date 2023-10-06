# .gitignore가 작동하지 않을 때

깃의 캐시 문제로, 캐시 내용을 삭제 후 재커밋하면 된다.

```jsx
git rm -r --cached .
git add .
git commit -m "fix"
```