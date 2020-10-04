# javascriptFunc

# 1. 배열 splice 함수
## Array/splice.html


***

# 2. 배열 forEach 함수
## Array/forEach.html

## 1) 배열 forEach 함수
  - for문과 마찬가지로 반복적인 기능
  - 주어진 함수를 배열 요소 각각에 대해 실행한다.
  - 형태 
    > 1) 애로우 함수배열변수.forEach( 요소 ⇒ {...함수로직...} )
    > 2) 일반 함수 : 배열변수.forEach( function(요소){...함수로직...} )
  - 예 
```jsx
//1) 애로우 함수
  dataArr.forEach((element) => {
     console.log(element);
 });

//2) 일반 함수
dataArr.forEach(function (element) {
      console.log(element);
});
```

## 2) forEach의 callback함수의 3가지 인자
- forEach에서 실행하는 함수(callback함수)의 인자는 3가지가 있다.
- currentValue(첫번째 인자), index(두번째 인자), array(세번째 인자)
- 형태
    > 배열.forEach( (currentValue, index, array) ⇒ {  ... 함수로직.. } )
- 3가지 인자 : currentValue,  index, array

## 1) current
- callback함수의 첫번째 인자
- 현재 함수에서 실행하고 있는 배열의 요소
- 요소 값

## 2) index
- callback함수의 두번째 인자
- 현재 함수에서 실행하고 있는 요소의 index(번째)
- 요소 인덱스

## 3) array
- callback 함수의 세번째 인자
- forEach()를 호출한 배열
- 순회 중인 배열

```jsx
// current, index, array 
dataArr.forEach((currentValue, index, array) => {
   console.log(
      "현재 값 : " + currentValue,
      "현재 인덱스 : " + index,
      "현재 배열 : " + array
    );
});
```
# 3. forEach의 this 객체

- forEach문에서 참조할 객체
- 형태

> 배열.forEach( functtion(요소){... this활용....}, 객체 )

- 객체를 넣으면 this는 넣은 객체가 된다.

```jsx
let obj = { key: "키" };

dataArr.forEach(function (element) {
  console.log("현재 객체 : " + this.key, "현재 값 : " + element);
}, obj);

```

- 애로우 함수에서는 this를 사용하면, 고유한 this가 아닌 외부 this를 가져온다.

# 4. for문과 forEach의 차이

- for문과 forEach는 똑같이 반복을 한다는 것.
- for문은 반복문이고, **forEach는 반복문이 아닌 함수**이다.
- forEach는 함수를 인자로 받아 배열의 요소들을 실행한다.
- for문은 break문을 사용할 수 있으나, forEach문은 배열을 순회하므로 중간에 "break;" 문을 사용할 수 없다.
