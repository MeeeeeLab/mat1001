# Week 6：有限和、黎曼和与 Δx 的辨析

[返回目录](../README.md)

针对最近“如何讲解黎曼和”“如何从和式判断 a、b、Δx”的疑问提炼方法，不臆测未给出的原题具体表达式。

## 1. Σ 只是把每一项加起来，先看起点、终点与项数

> **课件定位：** [第 19 页：符号](../references/week6/page-019.webp)、[第 20 页：展开](../references/week6/page-020.webp)、[第 21 页：运算](../references/week6/page-021.webp)。

$\sum_{k=1}^n a_k=a_1+\cdots+a_n$。$k$ 是求和指标，可以一致改名；$n$ 在每个有限和中是固定的，取极限时才趋于无穷。

从 $k=m$ 到 $n$（整数且 $m\le n$）共有 $n-m+1$ 项。因此 $\sum_{k=1}^n c=nc$，但 $\sum_{k=0}^n c=(n+1)c$。与 $k$ 无关的因子可以移出求和号；$k$ 自身通常不能。

## 2. 常用求和公式：别把求和与幂交换

> **课件定位：** [第 21 页：常数和](../references/week6/page-021.webp)、[第 22 页：平方与立方和](../references/week6/page-022.webp)。

$$
\sum_{k=1}^n1=n,\qquad
\sum_{k=1}^n k=\frac{n(n+1)}2,
$$
$$
\sum_{k=1}^n k^2=\frac{n(n+1)(2n+1)}6,\qquad
\sum_{k=1}^n k^3=\left[\frac{n(n+1)}2\right]^2.
$$

其中一次和公式是补充回顾；其余对应上方课件。通常 $\sum a_k^2\ne(\sum a_k)^2$，右边还包含交叉项。

计算含 $n$ 的有限和：先展开并提取与 $k$ 无关的系数，再代公式，最后对完整表达式取极限。不能对每一项直接取极限后忽略项数也在变化。

## 3. 矩形近似的三件事：宽度、取样点、高度

> **课件定位：** [第 13 页：左端点](../references/week6/page-013.webp)、[第 14 页：右端点与中点](../references/week6/page-014.webp)、[第 27 页：等分公式](../references/week6/page-027.webp)。

把 $[a,b]$ 分成 $n$ 个等宽小区间：$\Delta x=(b-a)/n$。第 $k$ 段为 $[a+(k-1)\Delta x,a+k\Delta x]$。

| 取样方式 | $c_k$ |
| --- | --- |
| 左端点 | $a+(k-1)\Delta x$ |
| 右端点 | $a+k\Delta x$ |
| 中点 | $a+(k-\tfrac12)\Delta x$ |

矩形高度是 $f(c_k)$，不是 $c_k$ 本身；每一项为 $f(c_k)\Delta x$。**先确定宽度，再列点，最后代函数**，可以避免把取样点与函数值混淆。

## 4. 左和一定高估吗？要看单调性

> **课件定位：** [第 15 页：递减函数的上下估计](../references/week6/page-015.webp)。

对区间内连续函数，递增时左和不大于真实有符号累积值、右和不小于它；递减时相反。课件的 $1-x^2$ 在 $[0,1]$ 递减且非负，所以左和高估面积，右和低估。

**补充辨析：** 函数不单调时，固定的左/右端点不一定在每段取到最大/最小值。“上和”按每段上确界取高度，“下和”按每段下确界取高度；连续时就是段内最大/最小值。它们不总等于右和/左和。

中点法常更准，但不能仅凭这一页的例子断言对每个函数、每次划分都优于左右和。

## 5. 一般黎曼和不要求等分，真正关键是最长小段趋于 0

> **课件定位：** [第 25 页：划分](../references/week6/page-025.webp)、[第 26 页：宽度与取样点](../references/week6/page-026.webp)、[第 27–28 页：网格范数](../references/week6/page-027.webp)、[第 28 页例子](../references/week6/page-028.webp)。

给定 $a=x_0<\cdots<x_n=b$，令 $\Delta x_k=x_k-x_{k-1}$，任选 $c_k\in[x_{k-1},x_k]$，得到

$$
S_P=\sum_{k=1}^n f(c_k)\Delta x_k,\qquad \|P\|=\max_k\Delta x_k.
$$

等分只是特例。课件的不等分例子每段宽度不同，不能把共同的 $(b-a)/n$ 强行放在所有项外面。

**补充反例：** 即使段数增加，也可能一直保留 $[0,1/2]$ 不再分割，只细分后半段；此时最长宽度至少为 $1/2$，不算整体变细。一般积分极限要控制 $\|P\|\to0$，不是仅写“矩形越来越多”。

## 6. 从和式识别积分：a、b、Δx 必须与点列配套

> **课件定位：** [第 23 页：分割与右端点](../references/week6/page-023.webp)、[第 24 页：求和取极限](../references/week6/page-024.webp)、[第 27 页：标准形式](../references/week6/page-027.webp)。以下反向识别步骤是针对疑问的补充整理。

如果 $n$ 个矩形等分 $[0,1]$，就必须有 $\Delta x=1/n$；若用 $\Delta x=1/(2n)$，则 $n$ 段总长为 $1/2$。除非实际有 $2n$ 段，否则不能同时断定区间长为 1。

但是**和式前的系数不必整个都是 Δx**，它可能还含函数前的常数。以下两个解释都合法：

$$
\frac1{2n}\sum_{k=1}^n\left(\frac{k}{n}\right)^2
=\sum_{k=1}^n\frac12\left(\frac{k}{n}\right)^2\frac1n
\longrightarrow\int_0^1\frac{x^2}{2}\,dx,
$$

$$
\frac1{2n}\sum_{k=1}^n4\left(\frac{k}{2n}\right)^2
\longrightarrow\int_0^{1/2}4u^2\,du.
$$

它们都等于 $1/6$。所以识别方式可能不唯一；关键是**点列、段宽、函数和项数整体匹配**，不能只盯一个分母。

检查顺序：①共有几项；②选择一个合理的 $\Delta x$；③确认点列能写成 $a+k\Delta x$；④把剩余表达式写成 $f(c_k)$；⑤核对 $b=a+n\Delta x$。

## 7. 有限近似不等于极限；有符号面积不等于总面积

> **课件定位：** [第 24 页：极限思想](../references/week6/page-024.webp)、[第 26 页：正负矩形](../references/week6/page-026.webp)、[第 13 页：物理解释](../references/week6/page-013.webp)。

有限个矩形通常只是近似；只有在相应可积条件下，随划分整体变细得到共同极限，才记为定积分。严格的定积分定义是后续内容，见[OpenStax §5.2](https://openstax.org/books/calculus-volume-1/pages/5-2-the-definite-integral)（补充来源）。

速度为负时 $v\Delta t$ 为负，表示反向位移，不是负路程。课件第 13 页的例子速度非负，因此面积可表示路程；推广到变号速度时，总路程要累积 $|v|$，位移才累积 $v$。

## 自检问题

1. 如果有 $2n$ 个矩形，$[0,1]$ 上的等分宽度是多少？若只有 $n$ 个呢？
2. 若已知某段函数递减，左右端点中哪个会使每个矩形偏高？
3. 能否用“区间总长度 = 各段宽度之和”检查自己的 $a,b,\Delta x$？

[原函数](week6-antiderivatives-initial-values.md) · [积分补充工具](week6-integration-toolkit-supplement.md) · [页面索引](../references/README.md)
