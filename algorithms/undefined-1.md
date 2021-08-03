---
description: >-
  Regular expression(regex): 특정한 규칙을 가진 문자열의 집합을 표현하는 데 사용하는 형식 언어이다. (출처: 위키백과/
  내용 출처: 유튜브 드림코딩 by 엘리)
---

# 정규표현식

### 정규표현식 연습 사이트

{% embed url="https://regexr.com/5mhou" %}

### 기본 틀

\(ex\) /검색패턴/플래그 : // 사이에 패턴을 정해주고 그 뒤에는 flag가 붙는다.

### Flag

* i - ignore : 대소문자를 구분하지 않도록 설정.
* g - global : 일치하는 모든 부분을 선택하도록 설정.
* m - multi line : 문자열이 다중 라인이어도 문자열을 검색할 수 있도록 
* u
* y
* s

### Groups and ranges

| Character | Example | Description |
| :--- | :--- | :--- |
| \| | Hi\|Hello | Hi 또는 Hello 를 찾음 |
| \( \) | \(Hi\|Hello\)\|\(And\) |  \(Hi 또는 Hello\)그룹을 찾거나 \(And\)그룹을 찾 |
| \(?:\) | gr\(?:e\|a\)y    | \(grey\) 또는 \(gray\)그룹을 찾지만 그룹을 기억하지 않음   |
| \[ \] | \[a-z\] |  어떠한 문자열이든 a부터 z를 만족하면 찾음  |
| \[^\] | \[^a-zA-Z0-9\] |  \[ \]안에 해당하는 내용을 제외한 나머지를 찾음   |

### Quantifiers

| Character | Example | Description |
| :--- | :--- | :--- |
| ? | gra?y | a가 있거나 없거나 한 경우,gray와 gry를 찾음   |
| \* | gra\*y | 없거나 있거나 많거나 한 경우, gry/gray/graay.... |
| + | gra+y | 하나 또는 그 이상의 경우, gray/graay.... |
| {n} | gra{2}y | 갯수를 지정하여 찾음, graay |
| {min, } | gra{2,}y | 최소 갯수를 지정하여 찾음, graay/graaay..... |
| {min, max} | gra{2,3}y | 2개 이상 3개 이하를 찾음, graay/graaay |

### Boundary-type

| Character | Example | Description |
| :--- | :--- | :--- |
| \b | \bYa 또는 Ya\b | 단어 경계에 있는 것을 찾음, Ya로 시작하는 문자열/Ya로 끝나는 문자 |
| \B | \BYa 또는 Ya\B | 단어 경계에 있지 않은 것을 찾음, Ya로 시작하거나 끝나는 문자열은 찾지 않 |
| ^ | ^Ya | 문장\(한 줄?\)에서 시작하는 문자열을 찾음. |
| $ | Ya$ | 문장에서 끝나는 문자열을 찾음. |

### Character classes

| Character | Description |
| :--- | :--- |
| \ | 특수문자의 경우 \를 붙여야 찾을 수 있음 |
| . | 줄바꿈을 제외한 모든 문자를 찾음  |
| \d | 모든 숫자   |
| \D | 숫자를 제외한 모든 문자   |
| \w | 모든 문자   |
| \W | 문자를 제외한 것 |
| \s | 띄어쓰기 |
| \S | 띄어쓰기를 제외한 것들  |

