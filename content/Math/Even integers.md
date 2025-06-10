
> **Definition.** An integer $x$ is called **even** if and only if $x$ has the form $2k$ where $k$ is an integer.

看起来trivial，但怎么用$\forall,\exists$写？我们可以一个个把里面的信息分解出来

| Original text           | What it actually means    |
| ----------------------- | ------------------------- |
| x has the form $2k$     | $x = 2k$                  |
| where $k$ is an integer | $\exists k\in \mathbb{Z}$ |
因此我们其实可以写成 
$$
x\text{ is even} \iff \exists k\in\mathbb{Z}\text{ s.t. }x=2k.
$$

> [!Info] 小重点
> 1. 其实我并不喜欢where这个写法，因为where要看context，有时候代表$\forall$，有时代表$\exists$。上面更清楚的definition可以把$x$ has the form $2k$ where ...换成$x=2k$ for some ...。
> 2. 每个definition本质上都是if and only if的表述。有些author会写if罢了，为求简洁，但实际应该理解为if and only if。这个看起来像废话，但现实中我有跟朋友为了这个争吵过的经历，一直说"textbook这样写的mah"，真的难劝。
