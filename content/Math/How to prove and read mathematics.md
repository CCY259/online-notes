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

最典型的就是epsilon-delta definition，但我们暂缓先，不要吓到人
***
#### Even integers

> **Definition.** An integer $x$ is called **even** if and only if $x$ has the form $2k$ where $k$ is an integer.

看起来trivial，但怎么用$\forall,\exists$写？我们可以一个个把里面的信息分解出来

| Original text           | What it actually means    |
| ----------------------- | ------------------------- |
| x has the form $2k$     | $x = 2k$                  |
| where $k$ is an integer | $\exists k\in \mathbb{Z}$ |
因此我们其实可以写成
$$x\text{ is even} \iff \exists k\in\mathbb{Z}\text{ s.t. }x=2k.$$
> [!Info] 小重点
> 1. 其实我并不喜欢where这个写法，因为where要看context，有时候代表$\forall$，有时代表$\exists$。上面更清楚的definition可以把$x$ has the form $2k$ where ...换成$x=2k$ for some ...。
> 2. 每个definition本质上都是if and only if的表述。有些author会写if罢了，为求简洁，但实际应该理解为if and only if。这个看起来像废话，但现实中我有跟朋友为了这个争吵过的经历，一直说"textbook这样写的mah"，真的难劝。

---
#### Linearly independence
我们来看看书本的定义，摘自Abstract Algebra by David S. Dummit and Richard M. Foote。
![[Pasted image 20250605094529.png]]![[Pasted image 20250605094615.png|650]]

我们先不理Field和Vector Space是什么，我们来看看怎么“翻译”这个definition。
***

| 关键词                       | 他属于什么？                         | 描述中有没有$\forall$或$\exists$？                                         |
| ------------------------- | ------------------------------ | ------------------------------------------------------------------ |
| S                         | A subset of a vector space $V$ | 没有，我们在给它定义。<br>$S$ is called a set of linearly independent vectors |
| $\alpha_1,\dots,\alpha_n$ | scalars in $F$                 | with表示$\forall$                                                    |
| $v_1,\dots, v_n$          | vectors in $S$                 | with表示$\forall$                                                    |
**句子形式：** If (Property 1) with (Elements), then (Property 2).
**Property 1: $\alpha_1 v_1+\alpha_2v_2+\cdots+\alpha_n v_n = 0$
Property 2:** $\alpha_1=\alpha_2=\cdots=\alpha_n=0$
***
可以再拆分看：
1. $\alpha_1 v_1+\alpha_2v_2+\cdots+\alpha_n v_n = 0$ 这个没什么好说的，就是一个equation。
2. $\alpha_1=\alpha_2=\cdots=\alpha_n=0$ 还可以继续处理，我可以把这些index 1,...,n总结起来，用$\forall$来表达。我们可以将其表述为$$\forall i\in\{1,\dots, n\}, \alpha_i= 0.$$为什么要这么做？因为找negation的时候就会比较容易。

> [!summary] 想法总结：消除点点点
> 这里可以看出一个想法：看到一些statement喜欢用点点点$\cdots$的时候，我们经常可以把index写成set的形式，以便转化为可以用$\forall$或$\exists$的形式。
> 此想法甚至可以推广到infinite的case，比如$i\in I$, where $I$ is an infinite set，则$\forall i\in I$, $\alpha_i = 0$同样适用，当然这个definition不是这样define啦。 
> 如果只写点点点，是蛮不严谨的。
> 
> 此想法也激起一些讨论：$\alpha_1 v_1+\alpha_2v_2+\cdots+\alpha_n v_n = 0$也是有点点点哦？不用处理？
也可以处理的哦，毕竟我们有summation的notation，就是
$$\sum_{i=1}^n \alpha_iv_i = 0.$$
在这个情况，可有可无。
不过在特定情况，这个表述方式可以方便后续的计算，如一些number theory的题。
>
**不是说点点点不好用，而是要看处理情况。**
比如遇到telescoping series，而点点点在此时计算方面更占优势。

因此这个definition可以翻译为
$$\forall \alpha_1,\dots, \alpha_n\in F, v_1,\dots, v_n\in S,\alpha_1 v_1+\alpha_2v_2+\cdots+\alpha_n v_n = 0\implies \forall i\in\{1,\dots, n\}, \alpha_i= 0.$$
***

> [!faq] 问答环节
> 这里可能要乱了，可能有人会问以下几点：
> 1. 为什么要define到那么难看，为什么不直接用$v_1,\dots, v_n$，而是以$S$开始？
>    答：在ISM，我们并不会学到infinite-dimensional的case。
>    如果$S = \{v_1,\dots, v_n\}$，那么自然不需要理$S$是什么。
> 2. 酱直接拿infinite sum不是好咯？
>    答：infinite sum不应该被直接当作一个element。
>    举个例子，calculus学的是这个sum converge或diverge，并不代表他是一个“数字”。
>    可以这样理解: $1+1$是数字。$1+1+1+1+\cdots$ diverges，不是数字。如果infinite sum converges，那么我们才赋予他一个值，此时才会被当作一个element。
>    In general，我们都没有converge或diverge的概念了，因此这个东西不能适用。

***
反正infinite case不重要，我们就看看其他书本的definition吧。这次摘自Linear Algebra by Serge Lang。
![[Pasted image 20250605104309.png|650]]
这个表述很精妙，他的definition基本上就是从$\forall$和$\exists$转变而来的。
而且一开始就从linearly dependent开始，自然地强调了$\exists$的存在。
我对Serge Lang可是又爱又恨。他的一些书本细节省略太多，读到很痛苦。
这种留白方式，肯定是对我们太有信心了。

我们来慢慢解构他的definition。
***
**Linearly dependence over $K$的定义**

| 关键词              | 他属于什么？          | 描述中有没有$\forall$或$\exists$？                         |
| ---------------- | --------------- | -------------------------------------------------- |
| $v_1,\dots, v_n$ | Vectors in $V$  | 我们在给它定义<br>$v_1,\dots, v_n$ are linearly dependent |
| $a_1,\dots, a_n$ | Elements in $K$ | there exist表示$\exists$                             |
**句子形式：** There exist (Elements) (Property 1) such that (Property 2).
**Property 1:** $a_1,\dots, a_n$ not all equal to $0$
**Property 2:** $a_1v_1+\cdots +a_nv_n = 0$
***
继续解析$a_1,\dots, a_n$ not all equal to $0$，
index很难看，写成set就容易看。
其实他就是要表达$\exists i\in\{1,\dots, n\}\text{ s.t. } a_i\neq 0$.
***
因此这个definition可以写成
$$\exists a_1,\dots, a_n\in K\text{ s.t. } \exists i\in\{1,\dots, n\}\text{ s.t. } a_i\neq 0\text{ and }a_1v_1+\cdots +a_nv_n = 0.$$

> [!Tip] 改写方法
> 这里的句子形式是这样转化的：
> There exist (Elements) (Property 1) such that (Property 2)等同于There exist (Elements) such that (Property 1) and (Property 2)。
> 务必留意每一次的context，exist的情况不大会用到implies。

***
这个linearly dependence可以直接用来找出linearly independence的定义，就是拿negation：
$$\forall a_1,\dots, a_n\in K, a_1v_1+\cdots +a_nv_n = 0\implies \forall i\in\{1,\dots, n\},a_i=0.$$

我们来show一个set是linearly independent和一个set是not linearly independent。

> [!Statement]
> $(1,0), (0,1)$ are linearly indepedent over $\mathbb{R}$.

我不想算，所以只是想拿个超简单例子去看solution怎么写。
关于$\mathbb{R}$的部分，我要强调的是有些东西其实还没有写很清楚，就暂时只考虑用$\mathbb{R}$。
更多细节会在Statement 4提到。

根据上面的definition，我们就可以自己做出答案，根本不需要记忆什么template。
注意这里vector的0是(0,0)。
***
**Solution.** Let $\alpha_1,\alpha_2\in \mathbb{R}$ be scalars such that $\alpha_1 (1,0) + \alpha_2(0,1) = (0,0)$. Then $\alpha_1 = 0$ and $\alpha_2 = 0$. Hence $(1,0),(0,1)$ are linearly independent over $\mathbb{R}$. **Q.E.D.**
***

> [!Statement]
> $(0,0)$ is linearly dependent over $\mathbb{R}$.

同样道理，我用definition写出答案。
***
**Solution.** Take $\alpha_1 = 1\in \mathbb{R}$. Then $\alpha_1 \neq 0$ and $\alpha_1(0,0) = (0,0)$. So $(0,0)$ is linearly dependent over $\mathbb{R}$. **Q.E.D.**
***

> [!Info] 小重点
> 此时注意到，Serge Lang的definition多了"over $K$"这一个东西。
> 这个其实很重要，但多数人都带过。
> 简单来说，definition有强调那些element是在$K$里面，我们不能随意更换$K$。
> 选择不同的$K$会导致不一样的结果。
> 
> 当书本或者note没有over $K$的时候，需要看回context，比如整个chapter都在讲关于$\mathbb{R}$的话，我们就默认他在考虑over $\mathbb{R}$.

如果正在考虑complex number的case，可以看看下面statement的差别。

> [!Statement]
> $(i,0), (1,0)$ are linearly indepedent over $\mathbb{R}$.

这里我们会用到complex number的fact：We say that $$x_1+y_1i = x_2+y_2i\iff x_1=x_2\text{ and }y_1=y_2.$$这不是废话，待会会在[[#被滥用的=]]进一步说明。
***
**Solution.** Let $\alpha_1,\alpha_2\in\mathbb{R}$ be such that $\alpha_1(i,0) + \alpha_2(1,0) = 0$. Then $\alpha_1i + \alpha_2 = 0$. So $\alpha_1= 0$ and $\alpha_2 = 0$. Hence $(i,0),(1,0)$ are linearly independent over $\mathbb{R}$. **Q.E.D.**
***

> [!Statement]
> $(i,0), (1,0)$ are linearly depedent over $\mathbb{C}$.

***
**Solution.** Take $\alpha_1 = i$ and $\alpha_2 = 1$. Then $\alpha_1,\alpha_2\in\mathbb{C}$, $\alpha_1,\alpha_2\neq 0$ and $\alpha_1(i,0) + \alpha_2(1,0) = (-1,0)+(1,0) = (0,0)$. Hence $(i,0),(1,0)$ are linearly dependent over $\mathbb{C}$.
**Q.E.D.**
***
#### Independent events
Following Dr. Khang's note, he said that
 
> In general, for $n$ events $A_1,A_2,\dots, A_n$, they are independent if and only if the probability of the intersections of two, three, four, up to all $𝑛$ events can be expressed as the product of the probability of each event.

这里我想提醒一下比较严谨的地方，以防以后再学乱掉。
其实我们有三个不同的有关independent的定义: 
(1) Pairwise independent; 
(2) Mutually independent; 
(3) Independent.

> **Definition.**
> (1) Pairwise independent: The events $A_1,\dots, A_n$ are **pairwise independent** if $$P(A_i\cap A_j) = P(A_i)P(A_j) \text{ for all } i,j\in\{1,\dots, n\}, i\neq j.$$(2) Mutually independent: The events $A_1,\dots, A_n$ are **mutually independent** if$$P(A_1\cap A_2\cap\cdots \cap A_n) = P(A_1)P(A_2)\cdots P(A_n).$$(3) Independent: The events $A_1,\dots, A_n$ are **independent** if for all $I\subseteq\{1,\dots, n\}$,$$P\left(\bigcap_{i\in I}A_i\right) = \prod_{i\in I}P(A_i).$$

第三个是Dr Khang用的定义，但更加formal，运用到了之前”消除点点点“的想法。

我们现在回答一些statement：

> [!Statement]
> Let $A_1,\dots, A_n$ be events. If $A_1,\dots, A_n$ are independent, then $A_1,\dots, A_n$ are pairwise independent.

这个statement是对的，但现在需要写出proof来解释。
先unpack所有definitions: $\forall A_1,\dots, A_n, (A_1,\dots, A_n\text{ are independent})\implies (A_1,\dots, A_n\text{ are pairwise independent})$. 
虽说是unpack，不过如果def太大，我们可以用括弧解释先。

写出所有hypothesis和conclusion先。
这个时候写越清楚越好，可能写solution会用到。

| Hypothesis                                                                                           | Conclusion                                                                        |
| ---------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| For all $I\subseteq\{1,\dots, n\}$,<br>$$P\left(\bigcap_{i\in I}A_i\right) = \prod_{i\in I}P(A_i).$$ | $$P(A_i\cap A_j) = P(A_i)P(A_j) \text{ for all } i,j\in\{1,\dots, n\}, i\neq j.$$ |

我们可以把
$$P(A_i\cap A_j) = P(A_i)P(A_j) \text{ for all } i,j\in\{1,\dots, n\}, i\neq j$$
写成
$$\forall i,j\in\{1,\dots, n\}\,(i\neq j), P(A_i\cap A_j) = P(A_i)P(A_j).$$
这个不太好看，其实我们可以把它写成
$$\forall i,j\in\{1,\dots, n\}, i\neq j\implies P(A_i\cap A_j) = P(A_i)P(A_j).$$
现在我们可以试试跟着Rule来写完整的solution。
***
**Solution.** Let $i,j\in\{1,\dots, n\}$ be such that $i\neq j$. Let $I = \{i,j\}\subseteq\{1,\dots, n\}$. Since $A_1,\dots, A_n$ are independent, we have $P\left(\bigcap_{i\in I}A_i\right) = \prod_{i\in I}P(A_i)$. So $P(A_i\cap A_j)  =P(A_i)P(A_j)$. Hence $A_1,\dots, A_n$ are pairwise independent. **Q.E.D.**
***

> [!Statement]
> Let $A_1,\dots, A_n$ be events. If $A_1,\dots, A_n$ are pairwise independent, then $A_1,\dots, A_n$ are independent.

这个statement是错的，那么我们就要try拿counterexample。
写solution的过程是可以直接看Statement 2的**negation**做出来。

先找negation of $\forall A_1,\dots, A_n,(P\implies Q)$:
我们知道$$\sim(P\implies Q)\equiv \sim(\sim P \vee Q)\equiv P\wedge \sim Q.$$也就是说我们要show 
$$\exists A_1,\dots, A_n, (A_1,\dots, A_n \text{ are pairwise independent})\text{ and }(A_1,\dots, A_n \text{ are not independent}).$$
继续unpack definition: $A_1,\dots, A_n \text{ are not independent}$代表$$\exists I\subseteq\{1,\dots,n\}, P\left(\bigcap_{i\in I}A_i\right) \neq \prod_{i\in I}P(A_i).$$
这次没有hypothesis了，只有上面这个conclusion。
这个是counterexample的题型。

> [!info] 小重点
> 这里有个容易被忽略的重点，那就是**上面还不够完整**。
> 严格来说，他不是从event，而是从probability space开始。
> 这些算是所谓的hidden information。
> 因此做到要完整的话，一般就是**追到根源**（第一个define的东西）为止。
> 这题的话，就是看events从哪里来？从probability space来。
> Probability space从哪里来？已经没有哪里来了因为它是第一个define出来的。

***

> [!faq] What is probability space?
>  第一年学的时候并不知道**真正的**probability space是什么定义。
>  严谨来说，Probability space是三样东西组成，通常写为$(\Omega, \mathcal{F}, P)$.
>  
>  1. $\Omega$ is a **sample space**.
>  2. $\mathcal{F}$ is a set of subsets of $\Omega$, (set of events, and also called an $\sigma$**-algebra** or **event space**) satisfying the following:
> 	- $A\in \mathcal{F}\implies A^c\in \mathcal{F}$;
> 	- $A_i\in\mathcal{F} (i\in I)\implies \bigcup_{i\in I}A_i\in\mathcal{F}$. (这里的$I$是countable set)
> 3. $P:\mathcal{F}\rightarrow [0,1]$ is a **probability measure**, that is,
> 	- $P(\Omega) = 1$;
> 	- Let $A_i$ $(i\in I)$ be mutually disjoint events (countably many), then$$P\left(\bigcup_{i\in I}A_i\right) = \sum_{i\in I}P(A_i).$$
> 
> 一开始不去介绍清楚，是因为他的definition包含的信息过多，新手或许处理不来。
> 但总之，probability space就是$(\Omega, \mathcal{F}, P)$，我们应该把这个triple当作一个object。

因此我们是要做$\exists\text{Sample space } \Omega, \exists \sigma\text{-algebra/event spaces } \mathcal{A} ,\exists\text{probability measure }P:\mathcal{A}\rightarrow[0,1], \exists A_1,\dots, A_n\in\mathcal{A}$ such that $(A_1,\dots, A_n \text{ are pairwise independent})\text{ and }(A_1,\dots, A_n \text{ are not independent}).$

现在来写solution。
***
**Solution.** The statement is false. Take $\Omega =\{x_1,x_2,x_3,x_4\}$. Let the event space $\mathcal{A}$ be the set of all subsets of $\Omega$ and assume that outcomes are equally likely. Set $$A_1 = \{x_1,x_2\},\quad A_2 = \{x_1,x_3\},\quad A_3 = \{x_1,x_4\}.$$Note that $$\begin{gather}P(A_1) = P(A_2) = P(A_3) = 1/2,
\\
P(A_1\cap A_2) = P(A_1\cap A_3) = P(A_2\cap A_3) = 1/4,
\\
P(A_1\cap A_2\cap A_3) = 1/4.\end{gather}$$By the first two equations, $A_1,A_2,A_3$ are pairwise independent. 
But $$P(A_1\cap A_2\cap A_3) = 1/4\neq 1/8 = P(A_1)P(A_2)P(A_3).$$So $A_1,A_2,A_3$ are not independent. **Q.E.D.**
***

> [!info] Remarks
> 1. "outcomes are equally likely" 需要写出来才可以算probability，这里是在表示你在construct一个probability measure $P:\mathcal{A}\rightarrow [0,1]$ by $$P(A) = \frac{|A|}{|\Omega|}.$$一般上很多人都跳过此细节，包括event space也是。如果在某些书你没看到event space，那么你可以assume他在用the set of all subsets of $\Omega$.
> 2. Counterexample直接看答案容易，要自己construct很难，原因很大在于没有motivation，只能自己翻遍很多cases来找。
> 3. Calculations的地方乱来没问题，conclusion写好来就ok。

#### Epsilon-Delta definition
这是在说limit of a function。

> [!attention] 注意
> 这个definition算是理解过程的重灾区，因为definition会根据学生的水准而改变。
> Graduate level的，会写得非常严谨仔细。第一年的就很随便。

我们来看看一些书本怎么define。
摘自Real Analysis: Foundations and Functions of One Variable by Laczkovich and Sós
![[Pasted image 20250606104837.png|650]]
我不太喜欢这样子写，因为太多细节消失了。
比如我看到的以下缺陷：
1. $f$很难写成$f:D\rightarrow \mathbb{R}$的形式，这里$D$**不一定**是open inverval containing $a$，因为他写了$f$不一定defined at $a$ (excluding perhaps $a$ itself)。
2. $0<|x-a|<\delta$的part有$x$，它是什么？In $D$ or in other subsets？
   原文并未强调，$x$必须属于$D$，不能随便取。
3. 为什么要open，为什么要interval，为什么一定要containing? 如果我define在subset and it does not contain $a$会有什么问题？

当然有些原因是因为有些concept还没学（例如limit point），不能说到太清楚。
但讲难听点，这样子的写法，害到很多人都不懂自己在写什么，大多数就是死记硬背，什么concept都不知道。
当遇到更严谨的定义，会因为以前死记的关系，导致混淆概念，也很难接受新的定义。
**更严谨的definition**，需要引入新的概念，叫limit point或accumulation point，在advanced calculus会学到。

为了方便我们let $D$ be the domain of $f$ as described in the definition. Then the definition is translated to$$\lim_{x\rightarrow a}f(x)=b\iff \forall \epsilon>0, \exists \delta>0\text{ s.t. }\forall x\in D, 0<|x-a|<\delta\implies |f(x)-b|<\epsilon.$$
***
可以试试简单function。

>[!note] Statement
> Let $f:\mathbb{R}\rightarrow \mathbb{R}$ be defined by $f(x) =x^2$. Then $\lim_{x\rightarrow 2} f(x) = 4$.

这个算是第一个不能直接用definition做到的题目，需要引入工具。

因为$\delta$是需要自己construct的，只要他是大过0都可以，这给予了我们很多自由。
通过$0<|x-2|<\delta$，我们可以自己在加入一些conditions来帮我们找到答案。

如果$0<|x-2|<\delta$ holds，但我还想要以下conditions
$$\begin{gather*}|x-2|<c_1
\\
|x-2|<c_2
\\
\vdots
\\
|x-2|<c_n\end{gather*}$$
where $c_i > 0$ for all $i\in\{1,\dots, n\}$.
那么应该就set $\delta = \min\{c_1,c_2,\dots, c_n\}$。
为什么？我们慢慢分析，假如$c_k$是最小的。Then $\delta = c_k$.
If $0<|x-2|<\delta$, then $|x-2| < c_k \leq c_i$ for all $i\in\{1,\dots, n\}$, $i\neq k$.
那么我们就可以得到以上conditions了。

然后如果我们有新的condition，我们就再update新的$\delta$。
比如我要上面全部condition，再加多一个$$\delta < 2025$$那么我就set $\delta = \min\{c_1,c_2,\dots, c_n,2024\}$.
也可以set $\delta = \min\{c_1,c_2,\dots, c_n,1\}$，要set什么都可以，只要那个号码小过2025都没问题。
不过每次加和$\delta$有关的condition就用$\leq$好过用$<$，不用那么为难自己。
如果我要$$\delta \leq 20252025$$那就直接拿$\delta = \min\{c_1,c_2,\dots, c_n,20252025\}$，简单直接，不用烦恼小不小大不大。

但现在要加什么还不清楚，这里就是要看我们要show的东西，也就是$|x^2-4|<\epsilon$。
这里可以看到$$x^2-4=\underbrace{(x-2)}_{在hypothesis出现}\cdot(x+2).$$所以我们可以try apply hypothesis看拿到什么：$$|x^2-4| = |x-2||x+2|<\delta|x+2|.$$现在要加condition，让我们的流程长这样。
$$|x^2-4| = |x-2||x+2| <\delta|x+2|\leq \underbrace{\cdots}_{\text{某些condition}}\leq \varepsilon.$$
其实我可以就加个$$|x-2|<1$$原因是我只是想要把$|x+2|$消灭掉，然后我们可以注意到$$|x+2|=|x-2+4| \leq |x-2|+|4|<1+4=5.$$这里就用了外来工具：Triangle Inequality $|x+y|\leq |x|+|y|$ for all $x,y\in\mathbb{R}$.

So if$|x-2|<1$ holds, then $|x+2|<5$. Hence$$|x^2-4|=|x-2||x+2|<\delta|x+2|<5\delta.$$但我要$|x^2-4|<\epsilon$，那就再加多一个condition
$$5\delta \leq \epsilon$$但这个是$$\delta\leq \varepsilon/5$$所以我应该拿$\delta = \min\{\frac{\epsilon}{5},1\}$。

解答流程就应该长这样 
***
**Solution.** Let $\epsilon>0$. Take $\delta = \min\{\frac{\epsilon}{5},1\}$. 
Let $x\in\mathbb{R}$ be such that $0<|x-2|<\delta$. 
Since $|x-2|<1$, it follows from the triangle inequality that$$|x+2|=|x-2+4| \leq |x-2|+|4|<1+4=5.$$Hence$$|x^2-4|=|x-2||x+2|<\delta|x+2|<5\delta\leq \epsilon.$$Therefore $\lim_{x\rightarrow 2} f(x) = 4$. **Q.E.D.**
***
现在来做个**不要想太多**的题目

>[!note] Statement
>Let $c,d\in\mathbb{R}$. Let $f:\mathbb{R}\setminus\{d\}\rightarrow \mathbb{R}$ be defined by $f(x)=c$. Then $\lim_{x\rightarrow d}f(x) = c$.

这里就没有什么zabalang conditions了。其实我们随便construct $\delta$都会对。
因为如果let $x\in \mathbb{R}\setminus\{d\}$ with $0<|x-d|<\delta$, 那么会看到$x\neq d$。
By definition of $f$, we immediately know that $f(x) = c$, and so $|f(x)-c|=0$.

所以怎样都会找到答案，就随便拿个数字。
唯一值得注意的是$f$的domain不要搞错，不是$\mathbb{R}$。
***
**Solution.** Let $\epsilon >0$. Take $\delta = 2025>0$. 
Then for all $x\in\mathbb{R}\setminus\{d\}$ with $0<|x-d|<\delta$, we have $f(x) = c$. 
So $$|f(x)-c| = 0<\epsilon.$$Hence $\lim_{x\rightarrow d}f(x) = c$. **Q.E.D.**
***
这告诉我们别一开始就加condition。

我们再看多一题，处理方式差不多，也是用到额外的fact。

>[!note] Statement
>Let $f:\mathbb{R}\setminus\{0\}\rightarrow \mathbb{R}$ be defined by $f(x)=|x|^{2025}\sin \frac{1}{x}$. Then $\lim_{x\rightarrow 0}f(x) = 0$.

***
Solution. Let $\epsilon>0$. Take $\delta = \epsilon^{1/2025}>0$. 
Let $x\in\mathbb{R}\setminus\{0\}$ be such that $0<|x-0|<\delta$. 
Since $|\sin y|\leq 1$ for all $y\in\mathbb{R}$, we have $|\sin \frac{1}{x}|\leq 1$.
This implies $$\left||x|^{2025}\sin \frac{1}{x}-0\right| = |x|^{2025} \left|\sin \frac{1}{x}\right|\leq |x|^{2025}<\delta^{2025} = (\epsilon^{1/2025})^{2025}=\epsilon.$$Therefore $\lim_{x\rightarrow 0}f(x) = 0$. **Q.E.D.**
***
关键步骤就是注意到$|\sin y|\leq 1$，用这个来消灭$|\sin \frac{1}{x}|$。

以上讨论可以总结成几点：

>[!summary] 想法总结
>如果情况允许，我们可以**添加额外条件**来简化问题。

> [!Tip] 技巧
> 1. 在Epsilon-Delta definition里，我们常通过$\delta = \min\{\cdots\}$来增加额外条件。
> 2. 时常把hypothesis和conclusion关联在一起。第一题里面的关键观察为$x^2-4 = (x-2)(x+2)$。
> 3. *Triangle inequality*和$|\sin x|,|\cos x|\leq 1$是处理absolute value的好工具。

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

