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
**Property 1:** $\alpha_1 v_1+\alpha_2v_2+\cdots+\alpha_n v_n = 0$
**Property 2:** $\alpha_1=\alpha_2=\cdots=\alpha_n=0$
***
可以再拆分看：
1. $\alpha_1 v_1+\alpha_2v_2+\cdots+\alpha_n v_n = 0$ 这个没什么好说的，就是一个equation。
2. $\alpha_1=\alpha_2=\cdots=\alpha_n=0$ 还可以继续处理，我可以把这些index 1,...,n总结起来，用$\forall$来表达。我们可以将其表述为$$
\forall i\in\{1,\dots, n\}, \alpha_i= 0.
$$为什么要这么做？因为找negation的时候就会比较容易。

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
>**不是说点点点不好用，而是要看处理情况。**
>比如遇到telescoping series，而点点点在此时计算方面更占优势。

因此这个definition可以翻译为$$
\forall \alpha_1,\dots, \alpha_n\in F, v_1,\dots, v_n\in S,\alpha_1 v_1+\alpha_2v_2+\cdots+\alpha_n v_n = 0\implies \forall i\in\{1,\dots, n\}, \alpha_i= 0.
$$
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
$$
\exists a_1,\dots, a_n\in K\text{ s.t. } \exists i\in\{1,\dots, n\}\text{ s.t. } a_i\neq 0\text{ and }a_1v_1+\cdots +a_nv_n = 0.
$$

> [!Tip] 改写方法
> 这里的句子形式是这样转化的：
> There exist (Elements) (Property 1) such that (Property 2)等同于There exist (Elements) such that (Property 1) and (Property 2)。
> 务必留意每一次的context，exist的情况不大会用到implies。

***
这个linearly dependence可以直接用来找出linearly independence的定义，就是拿negation：
$$
\forall a_1,\dots, a_n\in K, a_1v_1+\cdots +a_nv_n = 0\implies \forall i\in\{1,\dots, n\},a_i=0.
$$

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

这里我们会用到complex number的fact：We say that $$
x_1+y_1i = x_2+y_2i\iff x_1=x_2\text{ and }y_1=y_2.
$$这不是废话，待会会在[[#被滥用的=]]进一步说明。
***
**Solution.** Let $\alpha_1,\alpha_2\in\mathbb{R}$ be such that $\alpha_1(i,0) + \alpha_2(1,0) = 0$. Then $\alpha_1i + \alpha_2 = 0$. So $\alpha_1= 0$ and $\alpha_2 = 0$. Hence $(i,0),(1,0)$ are linearly independent over $\mathbb{R}$. **Q.E.D.**
***

> [!Statement]
> $(i,0), (1,0)$ are linearly depedent over $\mathbb{C}$.

***
**Solution.** Take $\alpha_1 = i$ and $\alpha_2 = 1$. Then $\alpha_1,\alpha_2\in\mathbb{C}$, $\alpha_1,\alpha_2\neq 0$ and $\alpha_1(i,0) + \alpha_2(1,0) = (-1,0)+(1,0) = (0,0)$. Hence $(i,0),(1,0)$ are linearly dependent over $\mathbb{C}$.
**Q.E.D.**
***
