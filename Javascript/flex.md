# 플렉스 박스(flex box) 레이아웃

> 뷰포트나 요소의 크기가 불명확하거나 동적으로 변할 때에도 (서로 다른 크기의 화면과  기기에서도) 효율적으로 요소를 배치, 정렬, 분산할 수 있는 방법

- 복수의 자식 요소 flex item과 상위 부모 요소 flex container로 구성
- flexbox를 만드는 방법 
부모 요소에 `display: flex` 선언

```jsx
.flex_container {
  display: flex;
}
```

- flex item은 main axis에 따라 정렬된다
- main axis는 flex-direction 속성으로 결정한다
- default는 row(가로) 정렬이다. 즉, 기본 방향이 row이면 main axis는 가로 cross-axis는 세로이다.
- main-axis 방향으로 item을 옮길 때는 justify-content를 사용한다.
- cross-axis 방향으로 item을 옮길 때는 align-items를 사용한다.


```
- 부모 요소에 정의하는 속성

    flex-direction // row 수평, column 수직 정렬 
    flex-wrap
    justify-content
    align-items
    align-content
```


```
- 자식 요소에 정의하는 속성

    flex
    flex-grow
    flex-shrink
    flex-basis
    order
```