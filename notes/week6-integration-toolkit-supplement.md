# Week 6 国内高数衔接：怎样寻找原函数

[返回目录](../README.md)

这是针对“复杂三角函数怎么得到原函数”的少量进阶工具。**本篇不是 Week 6 新增课件页的摘要**；超出课件的公式与方法均标为补充，不虚构课件页码。

## 1. 幂公式的例外与常用补全

> **课件基础：** [第 4 页：幂与三角公式](../references/week6/page-004.webp)。**补充来源：** [OpenStax §5.4：积分公式与净变化](https://openstax.org/books/calculus-volume-1/pages/5-4-integration-formulas-and-the-net-change-theorem)。以下对数、指数、反正切公式在 Week 6 无直接对应页。

$$
\int\frac1x\,dx=\ln|x|+C\quad(x\ne0),\qquad
\int e^x\,dx=e^x+C,\qquad
\int\frac1{1+x^2}\,dx=\arctan x+C.
$$

第一式在不跨 0 的区间使用，左右两区间的常数可独立。它不能由 $p\ne-1$ 的幂公式代入 $p=-1$ 得到。

## 2. 第一类换元法：找到内层，也找到它的导数

> **课件基础：** [第 4 页：常系数内层](../references/week6/page-004.webp)。**补充来源：** [同济大学“第一类换元积分法”](https://gaoshutongbu.tongji.edu.cn/info/1059/1207.htm)、[OpenStax §5.5](https://openstax.org/books/calculus-volume-1/pages/5-5-substitution)。一般换元法超出本周课件。

若 $F'=f$，链式法则给出 $[F(g(x))]'=f(g(x))g'(x)$。反向就得到

$$
\int f(g(x))g'(x)\,dx=F(g(x))+C.
$$

设 $u=g(x)$，相应 $du=g'(x)\,dx$，目的是把整个积分写成同一种变量。仅看见一个“内层”还不够，要核对导数因子。

**自拟小例子：** $\int 2x\cos(x^2)\,dx=\sin(x^2)+C$，因为 $x^2$ 的导数恰为 $2x$。而 $\int\cos(x^2)\,dx$ 缺少这个因子，不能直接写成 $\sin(x^2)/(2x)$；后者求导会产生额外项，必须另找方法。

不要把常数内层系数的“除以 k”推广成“任意复合都除以内层导数”。

## 3. 三角表达式先化简，不必看到复杂就换元

> **课件基础：** [第 6 页：线性运算](../references/week6/page-006.webp)。**补充来源：** [OpenStax Volume 2 §3.2：三角积分](https://openstax.org/books/calculus-volume-2/pages/3-2-trigonometric-integrals)。以下恒等变换的积分应用超出 Week 6。

例如利用 $\sin^2x=(1-\cos2x)/2$，可自行推导：

$$
\int\sin^2x\,dx=\frac x2-\frac{\sin2x}4+C.
$$

再对右边求导，得到 $(1-\cos2x)/2=\sin^2x$，完成检验。不要混淆 $\sin^2x$、$\sin(x^2)$ 与 $\sin(2x)$，它们结构不同，方法也不同。

## 4. 原函数与黎曼和将怎样接起来？

> **课件基础：** [第 2 页：原函数](../references/week6/page-002.webp)、[第 27 页：黎曼和](../references/week6/page-027.webp)。**补充来源：** [OpenStax §5.3：微积分基本定理](https://openstax.org/books/calculus-volume-1/pages/5-3-the-fundamental-theorem-of-calculus)。该定理本周未正式陈述，属于后续预告。

若 $f$ 在 $[a,b]$ 连续，且 $F'=f$，则

$$
\int_a^b f(x)\,dx=F(b)-F(a).
$$

原函数是一类函数；定积分是指定区间上的一个数。后者的 $C$ 在相减时消去，不需要在数值答案后加 $C$。它把“求和取极限”与“反向求导”联系起来，但不能因此跳过定义域和连续性等条件。

## 遇到陌生积分时，先问自己

1. 能否先展开、约分或用三角恒等式化简？
2. 哪一块像内层，它的导数是否也出现了？
3. 候选答案求导后，是否完整还原原式？

这是一套寻找与检验的起点，不保证每一个积分都能靠基本公式和一次换元完成。

[原函数笔记](week6-antiderivatives-initial-values.md) · [黎曼和笔记](week6-finite-sums-riemann-sums.md)
