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

为了方便我们let $D$ be the domain of $f$ as described in the definition. Then the definition is translated to$$
\lim_{x\rightarrow a}f(x)=b\iff \forall \epsilon>0, \exists \delta>0\text{ s.t. }\forall x\in D, 0<|x-a|<\delta\implies |f(x)-b|<\epsilon.
$$
***
可以试试简单function。

>[!note] Statement
> Let $f:\mathbb{R}\rightarrow \mathbb{R}$ be defined by $f(x) =x^2$. Then $\lim_{x\rightarrow 2} f(x) = 4$.

这个算是第一个不能直接用definition做到的题目，需要引入工具。

因为$\delta$是需要自己construct的，只要他是大过0都可以，这给予了我们很多自由。
通过$0<|x-2|<\delta$，我们可以自己在加入一些conditions来帮我们找到答案。

如果$0<|x-2|<\delta$ holds，但我还想要以下conditions
$$\begin{aligned}|x-2|&<c_1
\\
|x-2|&<c_2
\\
\vdots
\\
|x-2|&<c_n\end{aligned}$$where $c_i > 0$ for all $i\in\{1,\dots, n\}$.
那么应该就set $$\delta = \min\{c_1,c_2,\dots, c_n\}.$$为什么？我们慢慢分析，假如$c_k$是最小的。Then $\delta = c_k$.
If $0<|x-2|<\delta$, then $|x-2| < c_k \leq c_i$ for all $i\in\{1,\dots, n\}$, $i\neq k$.
那么我们就可以得到以上conditions了。

然后如果我们有新的condition，我们就再update新的$\delta$。
比如我要上面全部condition，再加多一个$$
\delta < 2025.
$$那么我就set $\delta = \min\{c_1,c_2,\dots, c_n,2024\}$.
也可以set $\delta = \min\{c_1,c_2,\dots, c_n,1\}$，要set什么都可以，只要那个号码小过2025都没问题。
不过每次加和$\delta$有关的condition就用$\leq$好过用$<$，不用那么为难自己。
如果我要$$
\delta \leq 20252025
$$那就直接拿$\delta = \min\{c_1,c_2,\dots, c_n,20252025\}$，简单直接，不用烦恼小不小大不大。

但现在要加什么还不清楚，这里就是要看我们要show的东西，也就是$|x^2-4|<\epsilon$。
这里可以看到$$
x^2-4=\underbrace{(x-2)}_{在hypothesis出现}\cdot(x+2).
$$所以我们可以try apply hypothesis看拿到什么：$$
|x^2-4| = |x-2||x+2|<\delta|x+2|.
$$现在要加condition，让我们的流程长这样。
$$
|x^2-4| = |x-2||x+2| <\delta|x+2|\leq \underbrace{\cdots}_{\text{某些condition}}\leq \varepsilon.
$$
其实我可以就加个$$
|x-2|<1
$$原因是我只是想要把$|x+2|$消灭掉，然后我们可以注意到$$
|x+2|=|x-2+4| \leq |x-2|+|4|<1+4=5.
$$这里就用了外来工具：Triangle Inequality $|x+y|\leq |x|+|y|$ for all $x,y\in\mathbb{R}$.

So if$|x-2|<1$ holds, then $|x+2|<5$. Hence$$
|x^2-4|=|x-2||x+2|<\delta|x+2|<5\delta.
$$但我要$|x^2-4|<\epsilon$，那就再加多一个condition
$$
5\delta \leq \epsilon
$$但这个是$$
\delta\leq \varepsilon/5
$$所以我应该拿$\delta = \min\{\frac{\epsilon}{5},1\}$。

解答流程就应该长这样 
***
**Solution.** Let $\epsilon>0$. Take $\delta = \min\{\frac{\epsilon}{5},1\}$. 
Let $x\in\mathbb{R}$ be such that $0<|x-2|<\delta$. 
Since $|x-2|<1$, it follows from the triangle inequality that$$
|x+2|=|x-2+4| \leq |x-2|+|4|<1+4=5.
$$Hence$$
|x^2-4|=|x-2||x+2|<\delta|x+2|<5\delta\leq \epsilon.
$$Therefore $\lim_{x\rightarrow 2} f(x) = 4$. **Q.E.D.**
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
So $$
|f(x)-c| = 0<\epsilon.
$$Hence $\lim_{x\rightarrow d}f(x) = c$. **Q.E.D.**
***
这告诉我们别一开始就加condition。

我们再看多一题，处理方式差不多，也是用到额外的fact。

>[!note] Statement
>Let $f:\mathbb{R}\setminus\{0\}\rightarrow \mathbb{R}$ be defined by $f(x)=|x|^{2025}\sin \frac{1}{x}$. Then $\lim_{x\rightarrow 0}f(x) = 0$.

***
Solution. Let $\epsilon>0$. Take $\delta = \epsilon^{1/2025}>0$. 
Let $x\in\mathbb{R}\setminus\{0\}$ be such that $0<|x-0|<\delta$. 
Since $|\sin y|\leq 1$ for all $y\in\mathbb{R}$, we have $|\sin \frac{1}{x}|\leq 1$.
This implies $$
\left||x|^{2025}\sin \frac{1}{x}-0\right| = |x|^{2025} \left|\sin \frac{1}{x}\right|\leq |x|^{2025}<\delta^{2025} = (\epsilon^{1/2025})^{2025}=\epsilon.
$$Therefore $\lim_{x\rightarrow 0}f(x) = 0$. **Q.E.D.**
***
关键步骤就是注意到$|\sin y|\leq 1$，用这个来消灭$|\sin \frac{1}{x}|$。

以上讨论可以总结成几点：

>[!summary] 想法总结
>如果情况允许，我们可以**添加额外条件**来简化问题。

> [!Tip] 技巧
> 1. 在Epsilon-Delta definition里，我们常通过$\delta = \min\{\cdots\}$来增加额外条件。
> 2. 时常把hypothesis和conclusion关联在一起。第一题里面的关键观察为$x^2-4 = (x-2)(x+2)$。
> 3. *Triangle inequality*和$|\sin x|,|\cos x|\leq 1$是处理absolute value的好工具。
