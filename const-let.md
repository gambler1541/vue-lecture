# const & let

> 새로운 변수 선언 방식

- 블록 단위 `{ }` 로 변수의 범위가 제한되었음
- `const` : 한번 선언한 값에 대해서 변경할 수 없음(상수 개념)
- `let` : 한번 선언한 값에 대해서 다시 선언할 수 없음

# 변수의 Scope

> 기존 자바스크립트(ES5)는 `{ }`에 상관없이 스코프가 설정됨

```
var sum = 0;
for(var i = 0; i <= 5; i++){
  sum = sum + i;
}
console.log(sum); // 15
console.log(i); // 6
```

### ES5 특징 - Hoisting

- Hoisting 이란 선언된 함수와 변수를 해석기가 가장 상단에 있는 것처럼 인식한다.
- js 해석기는 코드의 라인 순서와 관계 없이 함수선언식과 변수를 위한 메모리 공간을 먼저 확보한다.
- 따라서, `function a()` 와 `var` 는 코드의 최상단으로 끌어 올려진 것(hoisted)처럼 보인다.

```
function willBeOveridden() {
  return 10;
}

willbeOverridden(); // 5

function willbeOveridden() {
  return 5;
}
```

ES6

```
let sum =0;
for (let i = 0; i <= 5; i ++){
	sum += i;
}
console.log(sum); // 15
console.log(i); //  Uncaught ReferenceError: i is not defined
```

- const로 선언된 변수의 객체나 배열의 값은 변경이 가능하다.

```
const a = {};
a.num = 10;
console.log(a) // { num : 10}

const b = [];
b.push(10);
console.log(b) // [10]
```
