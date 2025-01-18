## Quiz 2

### 다음 코드에서 add 함수는 일급 객체로서 무엇을 수행하는가?

```
function add(x, y) {
  return x + y;
}

const myAdd = add;
console.log(myAdd(5, 3)); 
```

A. `add` 함수는 `myAdd`에 할당되고, 이를 호출할 수 있다.

B. `add` 함수는 `myAdd`에 할당되면 더 이상 호출할 수 없다.

C. `add` 함수는 인자로 전달할 수 없다.

D. `add` 함수는 다른 함수에 할당되면 변경될 수 없다.

<br>

## Answer 3

### myFunction은 함수이지만, 객체로 취급되어 description과 version이라는 프로퍼티를 가질 수 있다.

<br>


---

<br>


## Quiz 3

### 다음 코드는 **메모이제이션**을 적용한 예시이다. 이 함수는 어떤 동작을 하는가?

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

### 메모이제이션 기법을 사용하여 동일한 입력에 대해 계산을 한 번만 수행하고, 그 결과를 캐시에 저장하여 재사용한다.

**메모이제이션(Memoization)**은 주로 **동적 계획법(DP)**에서 사용되는 기법으로, 이미 계산한 값을 저장해 두고, 같은 계산이 반복되지 않도록 하는 최적화 기법이다.
-> 간단히 말하면, 중복된 계산을 피하기 위해 이전에 계산한 값을 "기억"하고 재사용하는 방식이다.

<br>
<br>

