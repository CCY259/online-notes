很多人数学学不好，因此才有了这个页面。
有些讲师连linearly independence的定义都能讲错，还有坚持$0⁰=1$这种暴论。
甚至以为ode学个Method of Undetermined Coefficients便足以solve所有题目。
讲师讲得喜羊羊，学生学得懒羊羊，考试出得灰太狼，最后成绩美羊羊。
实令本官欲投笔而赴汨罗矣。

本文应适用于各种偏理论类型科目，puremath受益最多，statistics也有一定的帮助，比如在学习probability theory，stochastic calculus等等。~~对Actuarial science并不会有任何帮助~~

~~这些东西为什么不是在basic math学~~
***
## Rules 
###### **Rule 1.** "Unpack" all definitions
- Unpack here means that we should write all the definitions in the following ways:
1. $\forall$ (called **Universal Quantifiers**) or $\exists$ (called **Existential Quantifiers**).
2. Statement P(x) involving variables.

总之，每个definition一般上分为两种：
1. （取名类型）给objects取名。
   比如$x$ is called Ali，什么作用不知道，我爽。
   Formal一点的话就比如Sample space $\Omega$。它其实就是Set而已，为什么取新名字？他爽，方便后面讨论。
   不一定专挑一个object取名词，我们可以挑两个以上的objects并赋予它们形容词。
   比如$x$ and $y$ are called "sama" if $x=y$。
2. （形式逻辑类型）这些可以写成$\forall x, P(x)$或$\exists x, P(x)$这两种形式。这里需要重点讲讲。

For No. 2, 很多书本都是直接用“句子”的形式写出来，所以我们需要自己阅读的时候进行“翻译”。

阅读过程可分为一下一个步骤：
1. 找出**关键词** (object)。
2. 找出**句子形式**（比如If ..., then ...)。
3. 判断描述的object有没有**for all** $\forall$还是**for some** $\exists$。

如果在阅读过程中，无法写出这种形式，可能是出现一下情况：
1. 理解不足。（建议重新把definition看过一遍，举例提升理解）
2. 作者自己定义错误。（可以翻找其他书本或Google，确认定义本身也没有问题）
3. 太多definition混杂在一起导致难以一个个取出info。（只能尽量分解步骤）
***
###### **Rule 2.** Specify/Understand hypothesis and conclusions (I mean what you want to show)
此Rule要配合Rule 3到Rule 7。把这些拆分开来，可以更加清楚答案怎么写，以及读proof可以更顺。
***
###### **Rule 3.** If you see "$\forall x\in S,P(x)$" in the hypothesis, then write "For all $x\in X$, we have $P(x)$", if you find an element $x\in S$ and want to use $P(x)$, then we can write "Since $x\in X$ (or just write the original hypothesis), we have $P(x)$".
- This is something you can use in proving a statement.
- Similar style of writing applies when $P(x)$ is replaced by $P(x)\implies Q(x)$. See the table below.
###### **Rule 4.** If you see "$\forall x\in S, P(x)$" in the conclusion, then write "Let $x\in S$ be given." or "Let $x$ be an element in $S$", and your aim is to show $P(x)$.
###### **Rule 5.** If you see "$\forall x\in S$, $P(x)\implies Q(x)$" in the conclusion, then write "Let $x\in S$ be an element such that $P(x)$.", and your aim is to show $Q(x)$.
###### **Rule 6.** If you see "$\exists x\in S, P(x)$" in the hypothesis, then write "There exists $x\in S$ such that $P(x)$".
###### **Rule 7.** If you see "$\exists x\in S, P(x)$" in the conclusion, then write "Take/Set/Let $x =$......".
- 这个一般上会用在写counterexample的时候。

为了方便查看，我把Rule 3-7做成table

|                                             | How we write in hypothesis                                                                                                                                                                                                                | How we write in Conclusion                                                            |
| ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| $\forall x\in S,P(x)$                       | If you want to mention all elements:<br>- For all $x\in S$, we have $P(x)$.<br><br>If you want to mention one element:<br>- Since $x\in S$, we have $P(x)$.                                                                               | - Let $x\in S$ be given.<br>- Let $x$ be an element in $S$.<br><br>(Then show $P(x)$) |
| $\forall x\in S$, $P(x)$<br>$\implies Q(x)$ | If you want to mention all elements:<br>- For all $x\in S$, we have $P(x)\implies Q(x)$.<br><br>If you want to mention one element:<br>- Since $x\in S$ and $P(x)$, we have $Q(x)$.<br>- Since $x\in S$ satisfies $P(x)$, we have $Q(x)$. | Let $x\in S$ be an element such that $P(x)$.<br><br>(Then show $Q(x)$)                |
| $\exists x\in S, P(x)$                      | There exists $x\in S$ such that $P(x)$.                                                                                                                                                                                                   | Take/Set/Let $x = ...$<br><br>(Then show $P(x)$)                                      |

 当然这不一定需要这样写，每个人有自己独特的写作方式。
 提升写作能力，可以参考各种书籍，模仿他们的句子。
 有些书本会带你去荷兰，要多加注意。
 我喜欢Terence Tao的写作方式，可以多看。

阅读能力方面，这些rule也可以帮助你理解他们在写什么。
但就如上面所说，有些作者写作风格可能会跳过很多东西，这时我们尽量用rule补充理解。
***
###### **Rule 8.** $P(x)\text{ for all }x\in S$ is the same as $\forall x\in S,P(x)$. 
- 我不知道为什么这个需要写出来，但感觉很多人好像不懂。
- 要我说差别，可能第一个是偏向language的表述，第二个偏向logic的表述吧。
***
###### **Rule 9.** $\exists x\forall y$ is not the same as $\forall y\exists x$. But $\exists x\exists y$ is the same as $\exists y \exists x$. The case $\forall x\forall y$ is the same as $\forall y\forall x$. Usually we don't write $\forall$ or $\exists$ more than once, so we write $\exists x,y$ to mean $\exists x\exists y$.
- 第一个不是一样意思的例子可以看epsilon-delta definition，但还是很抽象。

> [!Example] 乱来的例子
> 用"喜欢关系"说的话，设定P(x,y)为x喜欢y。
> 那么$\exists x \forall y, P(x,y)$代表存在一个x，喜欢所有y。
> 简单来说，有一个人(比如海王)，他喜欢所有人。
> 
> 而$\forall y \exists x , P(x,y)$代表每一个y，都存在某个x喜欢y。
> 简单来说，每个人都能找到至少一个人喜欢自己（比如父母，朋友）。
> 
> 关于
> $\forall x\forall y$和$\forall y\forall x$
> $\exists x\exists y$和$\exists y\exists x$
> 一样这回事：
> 第一个例子可以看linearly independence。
> 同样用回前面的例子的话，$\forall x\forall y, P(x,y)$代表每个人喜欢每个人，$\exists x\exists y, P(x,y)$代表有一个人喜欢一个人，对调也改变不了“每个人喜欢每个人”和“有一个人喜欢一个人”。

***
###### **Rule 10.** If you stuck, then try contradiction/contraposition.
- 严格来说这个不是和写法有关，而是作答技巧。
- Stuck是说你已经用尽所有definition和theorem（确保没有遗漏任何信息），还是找不到答案，那就应该用contradiction。
***
## 实践时间

最典型的就是epsilon-delta definition，但我们暂缓先，不要吓到人。
1. [[Even integers]]
2. [[Linearly independence]]
3. [[Independent events]]
4. [[Epsilon-Delta definition]]

#### Epsilon-Delta definition

***
## 其他一些小重点
#### If ... then ... 漏细节
很多人写if then的时候都miss掉$\forall$, for example, every even number is a multiple of two,写成statement时应该是$$\forall x\in \mathbb{Z}, (x\text{ is even})\implies (x\text{ is a multiple of two})$$而不是$$(x\text{ is even})\implies (x\text{ is a multiple of two}).$$像刚刚的statement，如果我只写~~Let A_1,..., A_n be events.~~ If $A_1,\dots, A_n$ are independent, then $A_1,\dots, A_n$ are pairwise independent，那么statement应该还是表达$$\forall A_1,\dots, A_n, (A_1,\dots, A_n\text{ are independent})\implies (A_1,\dots, A_n\text{ are pairwise independent})$$而不是$$(A_1,\dots, A_n\text{ are independent})\implies (A_1,\dots, A_n\text{ are pairwise independent}).$$
***
#### 被滥用的=
其实也不是滥用，而是=用在太多不一样的objects了。
每个equal，是可能有自己define的方法。

这里就写出一些普遍会遇到的=

| Objects         | Usual symbols                                               | Meaning of =                                                                                    |
| --------------- | ----------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Sets            | $A,B,C,\dots$                                               | $A=B$ iff $A\subseteq B$ and $B\subseteq A$.                                                    |
| Matrices        | $(a_{ij}),(b_{ij}),\dots$                                   | $(a_{ij})=(b_{ij})$ iff $a_{ij}=b_{ij}$ for all $1\leq i,j\leq n$.                              |
| Functions       | $f:A\rightarrow B$, $g:A\rightarrow B$, $\dots$             | $f=g$ iff $f(x)=g(x)$ for all $x\in A$.<br>Note that the domain and codomain are also the same. |
| Polynomials     | $p(x)=\sum_{i=0}^n a_i x^i$<br>$q(x) = \sum_{i=0}^m b_ix^i$ | $p=q$ (or $p(x)=q(x)$) iff $\deg p(x) = \deg q(x)$ and $a_i = b_i$ for all $i=1,\dots, n$.      |
| Complex numbers | $z_1=a_1+b_1i$, $z_2= a_2+b_2i$, $\dots$                    | $z_1=z_2$ iff $a_1=a_2$ and $b_1=b_2$.                                                          |
***
#### 阅读建议
有人和我说过数学很抽象，或许是因为还没有完全理解，也缺乏读这个东西的动机。

> [!note] 理解definition方面
最好的方式就是完整的写出来，然后标记每个statement的意义。
如果不知道它是干什么的，拿例子来证明，然后自己做个counterexample（做negation），久而久之会习惯这些statement，也容易记忆。

> [!note] 理解proof方面
第一阶段是从定义出发，锻炼你能不能观察出关键信息，这些proof通常都不会很难，都是从definition慢慢推导出答案。
>刚刚做的solution多数都是这个类型。
>
第二阶段是需要记忆并运用一些工具，处理细节就利用这个工具（一般都是大theorem）来证明，但难点就是我们需要自己意识到这个工具能用。其训练方式，可以在theorem那些里面梳理出适用的情况。
>这个并没有在note讨论到，唯一小theorem应该是triangle inequality。
>
第三阶段是锻炼想法（策略/技巧），这个没得救，没在书本看过就估计永远做不出来的那种。这种特别在它往往不会明写在theorem里，但proof也没有告诉你这是一种重要步骤。这时我们就要梳理整个证明，从里面找出最关键的那一步。然后试图找出其那么做的原因，和尝试思考不那么做会卡在哪里。悟出重点了，就总结成一个新想法，说不定在哪里可以运用到。
可以参考Epsilon-Delta definition那一部分，看我怎么持续地乱水，~~在班上这样子可是会被当废话的~~


> [!NOTE] 方面
> 方便面

