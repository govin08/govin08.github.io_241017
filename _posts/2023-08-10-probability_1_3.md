---
layout: single
title: "확률론 : 1.3. 조건부확률과 독립사건"
categories: mathematics
tags: [probability]
use_math: true
publish: false
author_profile: false
---

{% include /probability_intro/chatper_1.md %}

<style>
.center-table {
  text-align: center;
  margin: 0 auto;
  max-width: 100%;
  overflow: auto;
}
</style>

## 1.3. 조건부확률과 독립사건

### (1) 조건부확률

주사위를 던지는 시행에서 표본공간은

$$S=\{1,2,3,4,5,6\}$$

이었습니다.
또한, $A$를 짝수가 나올 사건이라고 하면,

$$A=\{2,4,6\}$$

이라고 쓸 수 있고 $P(A)$를

$$P(A)=\frac{n(A)}{n(S)}=\frac36=\frac12$$

로 계산할 수 있다고 했었습니다.
한편, $B$를 3의 배수가 나올 사건이라고 하면

$$B=\{3,6\}$$

이고

$$P(B)=\frac{n(B)}{n(S)}=\frac26=\frac13$$

입니다.

이번 파트에서 생각하는 것은 "주사위를 한 번 던져서 짝수($A$)가 나왔다고 가정할 때, 그 눈이 3의 배수($B$)일 확률"입니다.
짝수가 나오는 경우가 2, 4, 6의 세 경우이고, 이 중 3의 배수가 6밖에 없으므로 그 확률은 $\frac13$으로 계산할 수 있을 것입니다.
즉,

$$P(B\mid A)=\frac{n(A\cap B)}{n(A)}=\frac{n(\{6\})}{n(\{2,4,6\})}=\frac13$$

입니다.
이런 것을 조건부확률(conditional probability)이라고 하는데, 정확한 정의는 다음과 같습니다.

<div class="notice--info">
<b> 조건부확률 </b> <br>
두 사건 $A$, $B$에 대하여, $A$가 일어났을 때 $B$가 일어날 확률을 <b> 조건부확률 </b>이라고 부르고, $P(B\mid A)$로 적습니다.
$P(B\mid A)$의 값은
$$P(B\mid A)=\frac{P(A\cap B)}{P(A)}$$
으로 정의됩니다.
</div>

주사위를 한 번 던지는 시행에서 위의 정의와 아까의 계산에서 사용한 정의

$$P(B\mid A)=\frac{n(A\cap B)}{n(A)}$$

는 일치합니다.

$$\frac{n(A\cap B)}{n(A)}=\frac{\frac{n(A\cap B)}{n(S)}}{\frac{n(A)}{n(S)}} = \frac{n(A\cap B)}{n(A)}$$

이기 때문입니다.

$P(B\mid A)$를 계산했으니 반대로 $P(A\mid B)$도 계산해볼 수 있습니다.
이것은 "3의 배수($B$)가 나왔다고 가정할 때 그 눈이 짝수($A$)일 확률"입니다.
조건부확률의 정의에 의해

$$P(A\mid B)=\frac{P(A\cap B)}{P(B)}=\frac{\frac16}{\frac26}=\frac12$$

입니다.
아니면

$$P(A\mid B)=\frac{n(A\cap B)}{n(B)}=\frac12$$

와 같이 계산하여도 될 것입니다.

### (2) 독립과 종속

두 사건이 서로 영향을 미치지 않으면 두 사건을 독립이라고 합니다.
즉, 사건 $A$가 발생하는 것이 사건 $B$가 발생할 확률에 영향을 미치지 않는다면 (또 그 반대가 성립한다면) 두 사건이 독립적이라고 말할 수 있을 것입니다.
다시 말하면, 사건 $B$가 발생할 확률과, 사건 $A$가 발생했을 때 사건 $B$가 발생할 확률과, 사건 $A$가 발생하지 않았을 때 사건 $B$가 발생할 확률이 모두 같으면 두 사건이 독립적이라고 말할 수 있습니다.
수식으로 쓰면

$$P(B)=P(B\mid A)=P(B\mid A^c)$$

가 될 것입니다.
이것을 반대로 쓰면

$$P(A)=P(A\mid B)=P(A\mid B^c)$$

입니다.
다시 말해, 총 4개의 식

$$
\begin{align}
P(B)&=P(B\mid A)\tag a\\
P(B)&=P(B\mid A^c)\tag b\\
P(A)&=P(A\mid B)\tag c\\
P(A)&=P(A\mid B^c)\tag d
\end{align}
$$

이 성립하면 두 사건 $A$, $B$가 독립이라고 말할 수 있을 것입니다.
재미있는 것은 이 네 개의 식이 모두

$$P(A)P(B)=P(A\cap B)\tag e$$

와 필요충분조건의 관계에 있다는 것입니다.
분모가 0이 되는 상황을 피하기 위해 $P(A)\ne0$, $P(B)\ne0$을 가정하고 각각을 증명해보겠습니다.
먼저 $\text{(e)}$의 양변을 $P(A)$로 나누면

$$
P(B)=\frac{A\cap B}{P(A)}=P(B\mid A)
$$

가 되어 $\text{(a)}$가 성립합니다.
반대로 $\text{(a)}$식의 양변에 $P(A)$를 곱하면 (e)가 됩니다. 따라서 $\text{(a)}\iff\text{(e)}$ 입니다.
마찬가지의 논리를 적용하면 $\text{(c)}\iff\text{(e)}$ 입니다.
이번엔 $\text{(b)}$에서 출발해보면

$$
\begin{align*}
\text{(b)}
&\iff P(B)=P(B\mid A^c)\\[5pt]
&\iff P(B)=\frac{P(B\cap A^c)}{P(A^c)}\\[5pt]
&\iff P(B)P(A^c)=P(B-A)\\[5pt]
&\iff P(B)(1-P(A))=P(B)-P(A\cap B)\\[5pt]
&\iff P(B)-P(A)P(B)=P(B)-P(A\cap B)\\[5pt]
&\iff P(A)P(B)=P(A\cap B)\\[5pt]
&\iff \text{(e)}
\end{align*}
$$

입니다.
따라서 $\text{(b)}\iff\text{(e)}$이고, 마찬가지의 이유로 $\text{(d)}\iff\text{(e)}$ 입니다. $\square$

그러므로, 다음과 같이 독립의 개념을 정의할 수 있습니다.

<div class="notice--info">
<b> 독립과 종속 </b> <br>
$P(A)\ne0$, $P(B)\ne0$인 두 사건 $A$, $B$에 대하여 
$$P(A\cap B)=P(A)P(B)$$
이면 두 사건이 서로 <b>독립</b>이라고 말합니다.
한편, 두 사건이 서로 독립이 아니면, 두 사건이 서로 <b>종속</b>이라고 말합니다.
</div>

### (3) 독립과 종속 예시

예를 들어, (1)에서 $A$와 $B$는 독립입니다.

$$
\begin{align*}
A&=\{2,4,6\}\\
B&=\{3,6\}
\end{align*}
$$

에서

$$P(A\cap B)=\frac16=\frac12\times\frac13=P(A)P(B)$$

이기 때문입니다.
이때,

$$
\begin{align*}
P(A)&=\frac36\\
P(A\mid B)&=\frac12\\
P(A\mid B^c)&=\frac24
\end{align*}
$$

가 되어

$$
P(A)=P(A\mid B)=P(A\mid B^c)
$$

가 성립하는 것도 확인할 수 있습니다.

이와 같은 계산은

![]({{site.url}}\images\2023-08-10-probability_1_3\ABtable_0.png){: .img-30-center}

와 같이 $A$와 $B$를 표로 표현하면 쉽게 볼 수 있습니다.

![]({{site.url}}\images\2023-08-10-probability_1_3\ABtable_1.png){: .img-30-center}

에서 $P(A\mid B)=\frac12$이고

![]({{site.url}}\images\2023-08-10-probability_1_3\ABtable_2.png){: .img-30-center}

에서 $P(A\mid B^c)=\frac24$이며

![]({{site.url}}\images\2023-08-10-probability_1_3\ABtable_3.png){: .img-30-center}

에서 $P(A\mid B^c)=\frac36$이기 때문입니다.

$$
\begin{align*}
P(B)&=\frac26\\
P(B\mid A)&=\frac13\\
P(B\mid A^c)&=\frac13
\end{align*}
$$

가 되어

$$
P(B)=P(B\mid A)=P(B\mid A^c)
$$

가 성립하는 것도 확인할 수 있습니다.

한편, $C$를 소수가 나올 사건이라고 하면

$$C=\{2,3,5\}$$

이고,

$$P(A\cap C)=\frac16\ne\frac12\times\frac12=P(A)P(C)$$

이므로 $A$와 $C$는 서로 종속이라는 것을 알 수 있습니다.

이때,

$$
\begin{align*}
P(A)&=\frac36\\
P(A\mid C)&=\frac13\\
P(A\mid C^c)&=\frac23
\end{align*}
$$

가 되어 $P(A)$, $P(A\mid C)$, $P(A\mid C^c)$가 모두 다른 값을 가지는 것도 확인할 수 있습니다.

마찬가지로,

$$P(B\cap C)=\frac16=\frac13\times\frac12=P(A)P(C)$$

이므로 $A$와 $C$는 서로 독립입니다.

두 사건의 독립과 종속의 개념은 표를 통해서 보면 좀 더 선명하게 보일 수 있습니다.
여섯 개의 숫자들이 $A$에 속하는지 아닌지를 가로축으로, $B$에 속하는지 아닌지를 세로축으로 두어 표를 만들어보면

  |     |$A$|$A^c$|
  |:-:  |:-:|:-:  |
  |$B$  |6  |3    |
  |$B^c$|2,4|1,5  |
