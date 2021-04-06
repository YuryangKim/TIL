# position

작성 날짜: 2021년 4월 6일
해당 주제: htmlcss

# position 속성

- 태그 위치 설정 방법을 변경할 때 position 속성을 사용
- position 속성에 사용할 수 있는 키워드

-ms -page
absolute : 절대 위치 좌표 설정
fixed : 화면을 기준으로 절대 위치 좌표 설정 
inherit
initial
realative : 초기 위치 사태에서 상하좌우로 위치를 이동
static : 위에서 아래로, 왼쪽에서 오른쪽으로 순서대로 배치
sticky
unset

- HTML 페이지의 뒤에 입력한 태그가 상위에 올라간다
- 위치 순서를 변경하고 싶을 때는 z-index 속성으로 숫자를 적용한다.
숫자가 클 수록 앞에 위치한다.

```css
<style>

.box{
  width: 100px; height: 100px;
  position: absolute; 
}
.box:nth-child(1) {
  background-color: green;
	left: 10px top: 10px;
	z-index: 100;
}
.box:nth-child(2){
	background-color: purple;
	left: 50px top: 50px;
	z-index: 10;
}
.box:nth-child(3){
	background-color: yellow;
	left: 100px top: 100px
	z-index: 1;
}

// z-index를 주기 전에는 노란색 박스가 가장 위에 있으나, z-index 크기에 따라 초록색 박스가 제일 앞에 위치한다.
```

- position 속성에 absolute 키워드를 적용하면 부모 태그가 영역을 차지 하지 않는다. 
따라서 자손의 position 속성에 absolute 키워드를 적용할 경우, 부모 태그가 영역을 차지하게 만들기 위해서는 `첫번째, width,height` 를 주거나 `두번째, 부모의 position 속성에 relative 키워드를 적용한다.`

# overflow 속성

- 내부 요소가 부모의 범위를 벗어날 때 어떻게 처리할지 지정하는 속성
- overflow 속성에서 사용할 수 있는 키워드

hidden : 영역을 벗어나는 부분을 보이지 않게 만듦
scroll : 영역을 벗어나는 부분을 스크롤로 만듦 

- x,y 모든 축에 스크롤이 생성 되기 때문에 특정한 방향으로만 스크롤을 생성할 때는 overflow-x 속성과 overflow-y 속성을 사용한다

```css
body > div {
	oveflow-y: scroll;}
```