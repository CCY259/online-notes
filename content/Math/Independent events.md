Following Dr. Khang's note, he said that
 
> In general, for $n$ events $A_1,A_2,\dots, A_n$, they are independent if and only if the probability of the intersections of two, three, four, up to all $𝑛$ events can be expressed as the product of the probability of each event.

这里我想提醒一下比较严谨的地方，以防以后再学乱掉。
其实我们有三个不同的有关independent的定义: 
(1) Pairwise independent; 
(2) Mutually independent; 
(3) Independent.

> **Definition.**
> (1) Pairwise independent: The events $A_1,\dots, A_n$ are **pairwise independent** if $$
 P(A_i\cap A_j) = P(A_i)P(A_j) \text{ for all } i,j\in\{1,\dots, n\}, i\neq j.
 $$(2) Mutually independent: The events $A_1,\dots, A_n$ are **mutually independent** if$$
 P(A_1\cap A_2\cap\cdots \cap A_n) = P(A_1)P(A_2)\cdots P(A_n).
 $$(3) Independent: The events $A_1,\dots, A_n$ are **independent** if for all $I\subseteq\{1,\dots, n\}$,$$
 P\left(\bigcap_{i\in I}A_i\right) = \prod_{i\in I}P(A_i).
 $$

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

我们可以把$$
P(A_i\cap A_j) = P(A_i)P(A_j) \text{ for all } i,j\in\{1,\dots, n\}, i\neq j
$$写成$$
\forall i,j\in\{1,\dots, n\}\,(i\neq j), P(A_i\cap A_j) = P(A_i)P(A_j).
$$这个不太好看，其实我们可以把它写成$$
\forall i,j\in\{1,\dots, n\}, i\neq j\implies P(A_i\cap A_j) = P(A_i)P(A_j).
$$现在我们可以试试跟着Rule来写完整的solution。
***
**Solution.** Let $i,j\in\{1,\dots, n\}$ be such that $i\neq j$. Let $I = \{i,j\}\subseteq\{1,\dots, n\}$. Since $A_1,\dots, A_n$ are independent, we have $P\left(\bigcap_{i\in I}A_i\right) = \prod_{i\in I}P(A_i)$. So $P(A_i\cap A_j)  =P(A_i)P(A_j)$. Hence $A_1,\dots, A_n$ are pairwise independent. **Q.E.D.**
***

> [!Statement]
> Let $A_1,\dots, A_n$ be events. If $A_1,\dots, A_n$ are pairwise independent, then $A_1,\dots, A_n$ are independent.

这个statement是错的，那么我们就要try拿counterexample。
写solution的过程是可以直接看Statement 2的**negation**做出来。

先找negation of $\forall A_1,\dots, A_n,(P\implies Q)$:
我们知道$$\sim(P\implies Q)\equiv \sim(\sim P \vee Q)\equiv P\wedge \sim Q.$$也就是说我们要show $$
\exists A_1,\dots, A_n, (A_1,\dots, A_n \text{ are pairwise independent})\text{ and }(A_1,\dots, A_n \text{ are not independent}).
$$继续unpack definition: $A_1,\dots, A_n \text{ are not independent}$代表$$
\exists I\subseteq\{1,\dots,n\}, P\left(\bigcap_{i\in I}A_i\right) \neq \prod_{i\in I}P(A_i).
$$这次没有hypothesis了，只有上面这个conclusion。
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
> 	- Let $A_i$ $(i\in I)$ be mutually disjoint events (countably many), then$$
> 	- P\left(\bigcup_{i\in I}A_i\right) = \sum_{i\in I}P(A_i).
> 	- $$
> 
> 一开始不去介绍清楚，是因为他的definition包含的信息过多，新手或许处理不来。
> 但总之，probability space就是$(\Omega, \mathcal{F}, P)$，我们应该把这个triple当作一个object。

因此我们是要做$\exists\text{Sample space } \Omega, \exists \sigma\text{-algebra/event spaces } \mathcal{A} ,\exists\text{probability measure }P:\mathcal{A}\rightarrow[0,1], \exists A_1,\dots, A_n\in\mathcal{A}$ such that $(A_1,\dots, A_n \text{ are pairwise independent})\text{ and }(A_1,\dots, A_n \text{ are not independent}).$

现在来写solution。
***
**Solution.** The statement is false. Take $\Omega =\{x_1,x_2,x_3,x_4\}$. Let the event space $\mathcal{A}$ be the set of all subsets of $\Omega$ and assume that outcomes are equally likely. Set $$
A_1 = \{x_1,x_2\},\quad A_2 = \{x_1,x_3\},\quad A_3 = \{x_1,x_4\}.
$$Note that $$
\begin{aligned}P(A_1) &= P(A_2) = P(A_3) = 1/2,
\\
P(A_1\cap A_2) &= P(A_1\cap A_3) = P(A_2\cap A_3) = 1/4,
\\
P(A_1\cap A_2\cap A_3) &= 1/4.\end{aligned}
$$By the first two equations, $A_1,A_2,A_3$ are pairwise independent. 
But $$
P(A_1\cap A_2\cap A_3) = 1/4\neq 1/8 = P(A_1)P(A_2)P(A_3).
$$So $A_1,A_2,A_3$ are not independent. **Q.E.D.**
***

> [!info] Remarks
> 1. "outcomes are equally likely" 需要写出来才可以算probability，这里是在表示你在construct一个probability measure $P:\mathcal{A}\rightarrow [0,1]$ by $$
P(A) = \frac{|A|}{|\Omega|}.
$$一般上很多人都跳过此细节，包括event space也是。如果在某些书你没看到event space，那么你可以assume他在用the set of all subsets of $\Omega$.
> 1. Counterexample直接看答案容易，要自己construct很难，原因很大在于没有motivation，只能自己翻遍很多cases来找。
> 2. Calculations的地方乱来没问题，conclusion写好来就ok。
