# Typescript

###### TypeScript is Javascript with syntax for types



### TS에서 type을 지정하는 방법

```ts
// 1. 변수 선언 시 값과 타입을 함께 지정
const a : number = 1;
let b : boolean[] = [true, false];

// 2. 변수에 값 넣을 시 값 재할당 시 타입 추론
let c = "string type";
// c = 1; 은 허용되지 않음
```

### Object의 경우

```ts
const player : {
  name:string,
  age?:number
  // 물음표는 optional (age가 없어도 됨)
  // age를 지정해주지 않는다면 age = undefined
}= {
  name: "John",
  // age 는 optional
}
```

### Object Type 선언

```ts
type Player = {
  name : string,
  age? : number
}

const player : Player = {
	name: "John"
}
```

### 함수의 return type과 parameter type 지정

```ts
// Player 타입을 리턴하며 string과 number를 파라미터로 받는 함수 선언
function func( name:string, age:number ) : Player {
  return {
    name, age
  }
}
```

### type 에 readonly 속성을 추가

```ts
// Player의 name을 수정하려고 하면 에러 발생
type Player = {
  readonly name: string,
  age? : number
}

const numbers : readonly number[] = [1,2,3,4];
// numbers.push(1); 불가능
```

### Tuple

```ts
const player:[string, number, boolean] = ["name", 12, false];
```

### `any`

```ts
// any 타입으로 타입스크립트의 보호장치 비활성화
const a : any[] = [1,2,3,4];
const b = any = true;

// 허용 됨 any
a+b
```