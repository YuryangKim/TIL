# Bock element와 과 Inline element 구분
+강의 일시: 2021년 2월 23일
+해당 주제: htmlcss
---

- 한 라인에 복수로 올 수 있나 없나로 구분 가능
    - block element는 한 라인에 하나만 위치 ex)`<div>`
    - inline element는 한 라인에 2개 이상 위치 가능 ex)`<span>`
- 차이점
    - Block element는 Inline element를 포함할 수 있지만 Inline element는 block element를 포함 할 수 없다.

    **Block element**

    `p
    hi~h6
    ul
    ol
    pre
    dl
    div
    noscript
    blockquote
    form
    hr
    table
    fieldset
    address`

    **Inline element**

    `samp
    kbd
    var
    cite
    abbr
    acronym
    a
    img
    object
    br
    script
    map
    q
    sub
    sup
    span
    bdo
    input
    select
    textarea
    label
    button`

✔️ inline요소는 width 속성을 갖지 못하기 때문에 width 값을 갖게 하기 위해서는 block속성으로 바꿔야 한다.