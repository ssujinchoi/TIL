### text-align: 텍스트 정렬

inline, inline-block요소만 정렬된다.

상속되는 속성이다.

justify : 마지막 라이 제외하고 양쪽 끝으로 정렬 / 여백없이 다 채움, 비활성화시 단어별로 끊음

text-align의 initial 은 left

블럭레벨요소 인라인요소라고 말한다.



line-height: (line-height) - (font-size) 한 값을 leading영역에 절반 씩 할당하게 됨

수직정렬

1) padding, margin

2. line-height와 height를 맞추는 방법. 단, 글씨 길이가 2줄이상일 때는 수직정렬에 쓰지 못함
3. button은 자동으로 중간정렬 된다.
4. position: relative, top: 50% -> 텍스트 윗부분이 중간으로 오게됨.



line-height:1은 폰트사이즈와 동일하다는 

### vertical-align

**인라인요소** 의 수직 정렬



img는 inline속성이라 베이스라인이 있어서 공백이 생긴다.

default가 auto로 되어 있어서 자동으로 적용되는거 같아요



-webkit-line-clamp의 두번째 속성을 none으로 하면 ellipsis가 풀립니다



### position

의 기본값은 static

static일 때는 top, left, right 속성을 사용할 수 없다.





포지션이 statics를 제외한 값의 부모를 기준!!

1. 부모가 없으면 html기준!!
2. 

position을 사용했을 때, static과 ralative는 블록레벨 성질처럼 현재 컨텐츠의 영역을 차지하고, 그 외의 속성값들(absolute같은..)은 붕 떠있는 건가요?﻿ 그래서 겹치는 건가욤,,?? -> 네!!



position : static일 경우 z-index를 사용할 수 없다.



float을 이용하면 블록레벨요소도 왼쪽 오른쪽 정렬이 가능하다.

자기 자신이 가진 컨텐츠의 크기만큼만 자리를 점유하기 때문에 나란히 배치가 가능하다.



inline요소들은 float된 요소들을 알아본다.