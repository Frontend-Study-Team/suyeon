### 1. **원시값 비교**

<br>

원시값은 **값 자체**를 비교한다.

```jsx
let a = 10;
let b = 10;

console.log(a === b);

```

<br>

```jsx
let str1 = "hello";
let str2 = "hello";

console.log(str1 === str2);

```

<br>
<br>

### 2. **객체 비교**

<br>

객체는 **참조**를 비교한다. 즉, 동일한 데이터를 가진 객체라도 다른 참조를 가지면 다르게 취급된다.

```jsx
let obj1 = { name: "Alice" };
let obj2 = { name: "Alice" };

console.log(obj1 === obj2);

```

<br>
<br>

### 3. **객체의 참조 비교**

<br>

객체를 변수에 할당하면 참조가 복사된다. 같은 객체를 참조하는 두 변수는 `===` 비교 시 `true`를 반환한다.

```jsx
let obj3 = { name: "Alice" };
let obj4 = obj3;

console.log(obj3 === obj4);

```

<br>
<br>

### 4. **원시값을 객체처럼 다루기 (박싱)**

<br>

자바스크립트에서는 원시값을 객체처럼 다룰 수 있다. 예를 들어 문자열은 원시값이지만 메서드를 호출할 수 있다.

```jsx
let str = "hello";
console.log(str.toUpperCase());

```

<br>
<br>

### 5. **`null`과 `undefined` 비교**

`null`과 `undefined`는 특이한 동작을 한다.

```jsx
let a = null;
let b = undefined;

console.log(a === b); 
console.log(typeof a);  
console.log(typeof b);  

```
<br>
<br>
