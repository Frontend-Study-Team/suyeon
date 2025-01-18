## Quiz 3

다음 코드는 **메모이제이션**을 적용한 예시이다. 이 함수는 어떤 동작을 하는가?

```jsx
function memoizedAdd(x, y) {
  if (!memoizedAdd.cache) {
    memoizedAdd.cache = {};
  }

  const key = `${x},${y}`;
  if (key in memoizedAdd.cache) {
    return memoizedAdd.cache[key];
  }

  const result = x + y;
  memoizedAdd.cache[key] = result;
  return result;
}
```

A. 동일한 입력값에 대해 반복적인 계산을 방지한다.

B. `x`와 `y`의 값을 계속해서 더한다.

C. `memoizedAdd.cache`는 함수의 반환값을 저장한다.

D. `memoizedAdd.cache`는 함수의 인자값을 저장한다.

<br>

## Answer 3

```
function memoizedAdd(x, y) {
  if (!memoizedAdd.cache) {
    memoizedAdd.cache = {};  // 캐시 객체 초기화
  }

  const key = `${x},${y}`;  // x와 y의 값을 합친 문자열을 키로 사용
  if (key in memoizedAdd.cache) {
    return memoizedAdd.cache[key];  // 이미 계산된 값이 있으면 캐시된 값 반환
  }

  const result = x + y;  // 계산을 실행
  memoizedAdd.cache[key] = result;  // 계산된 결과를 캐시에 저장
  return result;
}
```
