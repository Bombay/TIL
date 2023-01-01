### 사용
flex와 마찬가지로 부모에 `display: grid` 선언으로 사용

## grid-template-columns
`grid-template-columns: 100px 100px 120px 10px` 4개 컬럼 width 지정

## grid-template-rows
`grid-template-rows: 10px 10px 20px 10px` 4개의 row height 지정

## column-gap
`column-gap: 10px` column 사이의 갭 지정

## row-gap
`row-gap: 20px` row 사이의 갭 지정

## gap
`gap: 10px` `column-gap` `row-gap`을 함께 지정

## repeat
`grid-template-columns: repeat(4, 250px)` `css grid function` 반복에 사용

## grid-template-areas
```
// 4x4 template 생성
grid-template-areas:
'header header header header'
'content content content nav'
'content content content nav'
'footer footer footer footer'
...

.header {
  grid-area: header;
}

.content {
  grid-area: content;
}
...
```

## grid-column, grid-row
```
// 첫번째 컬럼라인에서 4번째 라인까지 차지
grid-column: 1 / 4;
grid-column: 1/ -1; // -1 은 끝에서 첫번째 (-1, -2, ...)
grid-column: span 4; // 4개 block 차지

// 두번째 로우라인에서 4번째 라인까지 차지
grid-row: 2 / 4;
```
`grid-template-areas` 사용하지 않고 라인의 시작과 끝을 지정  

## fraction
`fraction` 은 기본적으로 사용 가능한 공간을 뜻함
```
// grid box 영역을 사용 가능한 공간으로 봄
display: grid;
grid-template-columns: repeat(4, 1fr);
grid-template-rows: repeat(4, 1fr);
```

## grid-template
row / column 지정으로 `grid-template-columns` `grid-template-rows` `grid-template-areas` 보다 간편하게 사용 가능
```
// grid-template-column 지정은 맨 마지막 줄에만 사용
grid-template:
'header header header header' 1fr
'content content content nav' 2fr
'footer footer footer footer' 1fr / 1fr 1fr 1fr 1fr // row 1fr, 나머지 column 1fr씩 지정
```

## justify-items, align-items, place-items
`justify-items` grid cell 가로 축 규칙  
`align-items` grid cell 세로 축 규칙
```
justify-items: stretch; // 가로 기본값. start, end, center ...
align-items: stretch; // 세로 기본값. start, end, center ...
place-items: center stretch; // 세로 가로 한번에 지정
```

## content, items 차이
content === grid  
items === cell  
grid element(container) !== grid // grid container는 말 그대로 container. grid는 그 안에 존재  

## justify-content, align-content, place-content
`justify-content` grid 가로 축 규칙  
`align-content` grid 세로 축 규칙  
```
// start, end, stretch, space-between, space-evenly ...
justify-content: start;
align-content: stretch;
place-content: start stretch;
```

## justify-self, align-self
`justify-items` `align-items` 를 cell에 단독으로 적용

## grid-auto-column, grid-auto-rows, grid-auto-flow
`grid-auto-column` `grid-auto-rows` 갯수 지정 없이 cell에 대한 규칙 설정  

`grid-auto-flow`: `flex-direction`과 비슷한 역할

## minmax
```
grid-template-columns: repeat(4, minmax(100px, 1fr));
```
