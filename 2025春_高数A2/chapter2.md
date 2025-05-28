---
title: 高等数学讲义(下)
author: 胡煜成
description: 首都师范大学2025春季学期高等数学A
"og:description": 浏览器版和手机版
"og:image": https://vlook-doc.pages.dev/pic/vlook-og.png
keywords:
- 高等数学,微积分,讲义
vlook-chp-autonum: h1{{第 ### 章 }},h3{{### }}
vlook-query: vdl=on
vlook-query: ws=off
---

[回到主页面](index.html)

# 多元函数的微分

> [!tip]
> 
> 多元函数的微分是一元函数微分的推广, 它的一个非常重要的应用是求多元函数的极值. 例如 (P115例6) 有一块宽为 24cm 的方形铁板, 把它两边折起来做成一个断面为等腰梯形的水槽, 问怎样的折法才能使得截面面积最大? 设折出来的梯形底边长度为 $x$, 斜边的角度为 $\theta$, 则截面积可写成
> 
> $$
> S(x, \theta) = 24 x \sin\theta - 2x^2 \sin\theta + x^2 \sin\theta \cos\theta
> $$
> 
> 这是一个关于 $x, \theta$ 的二元函数, 如何求它的最大值呢?  我们可以带着这个问题开始本章的学习.

## 多元函数的连续性
> [!tip]
> 
> 在一元微积分中, 连续函数是我们的主要研究对象, 在多元微积分中同样也是这样. 下面我们先介绍一些准备知识作为铺垫, 然后给出多元函数极限和连续的定义.
> 

### 区域

> [!tip]
> 
> 在一元函数中, 我们经常**区间**的概念, 如开区间 $(a, b)$, 闭区间 $[a, b]$. **区域**是区间在高维空间中的推广. 下面我们以 $\mathbb{R}^2$ 为例进行介绍, 但所有的概念都可以推广到 $\mathbb{R}^n$ 中.
> 

> [!important]
> 
> ==邻域==
> 
> 设 $P_0(x, y)$ 是 $\mathbb{R}^2$ 中的一点, 给定 $\delta > 0$,  $\mathbb{R}^2$ 中所有与点 $P_0$ 距离小于 $\delta$ 的点构成一个集合, 称为点 $P_0$ 的 **$\delta$-邻域**, 记作 $U(P_0, \delta)$, 即
>  $$
>   U(P_0, \delta) = \{ (x, y)| \sqrt{(x-x_0)^2+ (y-y_0)^2} < \delta\}.
> $$
> 
> $P_0$ 与其自己的距离为0, 所以根据上述定义, $P_0\in U(P_0, \delta)$. 但有时候我们希望排除掉 $P_0$ 这一点, 在集合 $U(P_0, \delta)$ 中把 $P_0$ 去掉, 由此得到的集合称为 $P_0$ 的 **$\delta$-去心邻域**, 记作 $\overset{\circ}{U}(P_0, \delta)$, 即
>  $$
>  \overset{\circ}{U}(P_0, \delta) = \{ (x, y)| 0 < \sqrt{(x-x_0)^2+ (y-y_0)^2} < \delta\}.
> $$
>
> 有时候我们不关心 $\delta$ 的具体取值 (比如接下来的问题中), 往往简单用 $U(P_0)$ 和  $\overset{\circ}{U}(P_0)$ 分别表示 $P_0$ 的**邻域**和**去心邻域**.
> 

> [!important]
> 
> ==内点==
> 
> 任意给定一个 $\mathbb{R}^2$ 中的集合 $D$, 任意一点 $P$ 与 $D$ 的关系比符合以下三种关系中的一种:
> 
> 1. **内点**: 存在点 $P$ 的某个邻域 $U(P)$, 使得  $U(P) \subset D$.
> 2. **外点**: 存在点 $P$ 的某个邻域 $U(P)$, 使得  $U(P) \cap D = \emptyset$.
> 3. **边界点**: 点 $P$ 的任一邻域内既有属于 $D$ 的点, 又有不属于  $D$ 的点.
> 
> 集合 $D$ 的全体**边界点**所构成的集合称为 $D$ 的**边界**, 记作 $\partial D$.
> 

> [!note]
> 
> ==例==
> 判断 $1 < x^2 + y^2 < 2$ 的内点, 外点和边界点.


> [!important]
> 
> ==聚点==
> 
> 对于点 $P$ 和点集 $E$，若对任意 $\delta > 0$，去心邻域 $ U^\circ(P, \delta) $ 内总包含 $E$ 中的点，则称 $P$ 是 $E$ 的**聚点**。
> 
> **注意**： 聚点 $P$ 可以**属于** $E$，也可以**不属于** $E$。
>

> [!note]
>
> ==例==
>
> 点集：$ E = \{ (x,y) \mid 1 < x^2 + y^2 \leq 2 \} $
> 
> 1. 内点：满足 $1 < x^2 + y^2 < 2$ 的所有点
> 2. 边界点：
>    - $x^2 + y^2 = 1$ 的点（不属于 $E$）
>    - $x^2 + y^2 = 2$ 的点（属于 $E$）
> 3. 聚点：$E$ 及其边界 $\partial E$ 上的所有点

> [!warning]
> 
> - 内点一定是聚点
> - 边界点可能是聚点
> - 聚点构成导集 $E'$，且 $\overline{E} = E \cup E'$
>

> [!important]
>
> ==开集与闭集==
>
> **开集**: 集合中的所有点都是其内点
> **闭集**: 集合的边界属于该集合, $\partial D \in D$
>

> [!note]
> 
> ==例==
> 
> 集合 $1 < x^2 + y^2 < 2$ 为开集.
>

> [!important]
> 
> ==连通集==
> 
> 顾名思义, 如果集合 $D$ 中的任意两点都可以用折线连接起来, 且该折线上的点都属于 $D$, 则称 $D$ 为**连通集**.

> [!important]
> 
> ==区域==
> 
> **连通开集**称为**区域**(或**开区域**); 开区域连同它的边界一起所构成的集合称为**闭区域**.
> 

> [!note]
> 
> ==例子== 
> 
> 集合 $\{(x,y) \mid 1 < x^2 + y^2 < 2\}$ 是区域，而集合 $\{(x,y) \mid 1 \leq x^2 + y^2 \leq 2\}$ 是闭区域.

> [!important]
> 
> ==有界集与无界集==
> > **有界集**  ： 对于平面点集 $E$，如果存在正数 $r$，使得$E \subset U(O, r)$，其中 $O$ 为坐标原点，则称 $E$ 为有界集。
> >**无界集** : 如果一个集合不是有界集，则称其为无界集。

### 多元函数的极限
> [!important]
> ==**多元函数的概念**==
> 设 $D$ 是 $\mathbb{R}^2$ 的一个非空子集，称映射 $f: D \to \mathbb{R}$ 为定义在 $D$ 上的**二元函数**，通常记为$ z = f(x, y), \quad (x, y) \in D $ 或 $ z = f(P), \quad P \in D。 $  
> 其中： 点集 $D$ 称为函数的**定义域** ，$x$ 和 $y$ 称为**自变量** ，$z$ 称为**因变量**  
> **函数值与值域**  ：对于自变量 $(x,y)$ 对应的因变量值 $z$（称为**函数值**），记作：$ z = f(x, y) $  
> 函数值的全体构成**值域**：  $ f(D) = \{ z \mid z = f(x, y), \ (x, y) \in D \} $

>[!important]
> ==**二元函数的极限**==
> 设二元函数 $f(P) = f(x,y)$ 的定义域为 $D$，$P_0 (x_0, y_0)$ 是 $D$ 的聚点。如果存在常数 $A$，对于任意给定的正数 $\varepsilon$，总存在正数 $\delta$，使得当点 $P(x,y) \in D \cap U(P_0, \delta)$ 时，都有$ |f(P) - A| = |f(x,y) - A| < \varepsilon $
> 成立，那么就称常数 $A$ 为函数 $f(x,y)$ 当 $(x,y) \to (x_0, y_0)$ 时的极限，记作 $ \lim_{(x,y) \to (x_0, y_0)} f(x,y) = A \quad \text{或} \quad f(x,y) \to A \left( (x,y) \to (x_0, y_0) \right), $ 也记作$ \lim_{P \to P_0} f(P) = A \quad \text{或} \quad f(P) \to A \left( P \to P_0 \right)$ ，为了区别于一元函数的极限，我们把二元函数的极限叫做==二重极限==。
>
> [!warning]
> **注意极限要求 $P$ 从各个方向趋近于 $P_0$, 仅仅是从 $x$ 和 $y$ 轴两个方向趋近是不够的.**
>
>**例1**. 设 $f(x,y) = (x^2 + y^2) \sin \frac{1}{x^2 + y^2}$，求证：$
> \lim_{(x,y) \to (0,0)} f(x,y) = 0.
> $
> 
> >**证** 这里函数 $f(x,y)$ 的定义域为 $D = \mathbb{R}^2 \backslash \{(0,0)\}$，点 $O(0,0)$ 为 $D$ 的聚点。
>因为 $|f(x,y) - 0| = \left| (x^2 + y^2) \sin \frac{1}{x^2 + y^2} - 0 \right| \leq x^2 + y^2,$ 
>可见，$\forall \varepsilon > 0$，取 $\delta = \sqrt{\varepsilon}$，则当$ 0 < \sqrt{(x-0)^2 + (y-0)^2} < \delta,$ 
>即 $P(x,y) \in D \cap U(0,\delta)$ 时，总有 $|f(x,y) - 0| < \varepsilon$ 成立，所以 $ \lim_{(x,y) \to (0,0)} f(x,y) = 0. $

> ---
>
>**例2**. 考察函数
> 
> $$ f(x,y) = 
> \begin{cases} 
> \frac{xy}{x^2 + y^2}, & x^2 + y^2 \neq 0, \\
> 0, & x^2 + y^2 = 0.
> \end{cases} $$
> 
> 显然，当点 $P(x,y)$ 沿 $x$ 轴趋于点 $(0,0)$ 时，
> 
> $$ \lim_{(x,y) \to (0,0)} f(x,y) = \lim_{x \to 0} f(x,0) = \lim_{x \to 0} 0 = 0; $$
> 
> 又当点 $P(x,y)$ 沿 $y$ 轴趋于点 $(0,0)$ 时，
> 
> $$ \lim_{(x,y) \to (0,0)} f(x,y) = \lim_{y \to 0} f(0,y) = \lim_{y \to 0} 0 = 0. $$
> 
> 虽然点 $P(x,y)$ 以上述两种特殊方式（沿 $x$ 轴或沿 $y$ 轴）趋于原点时函数的极限存在且相等，但是 $\lim_{(x,y) \to (0,0)} f(x,y)$ 并不存在。这是因为当点 $P(x,y)$ 沿着直线 $y = kx$ 趋于点 $(0,0)$ 时，有
> 
> $$ \lim_{(x,y) \to (0,0)} \frac{xy}{x^2 + y^2} = \lim_{x \to 0} \frac{kx^2}{x^2 + k^2 x^2} = \frac{k}{1+k^2}, $$
> 
> 显然它是随着 $k$ 的值的不同而改变的。
>
> ---

>**例3**. 求 $ \lim_{(x,y) \to (0,2)} \frac{\sin(xy)}{x} $
>
>>**解** 这里函数 $ \frac{\sin(xy)}{x} $ 的定义域为 $D = \{(x,y) | x \neq 0, y \in \mathbb{R}\}$，$P_0(0,2)$ 为 $D$ 的聚点。
>>由积的极限运算法则，得
>$\lim_{(x,y) \to (0,2)} \frac{\sin(xy)}{x} = \lim_{(x,y) \to (0,2)} \left[ \frac{\sin(xy)}{xy} \cdot y \right] = \lim_{xy \to 0} \frac{\sin(xy)}{xy} \cdot \lim_{y \to 2} y $ $=1 \cdot 2=2$
>
>---
>

### 多元函数的连续性

> [!important]
> 
> **==多元函数连续性的定义==**
>设二元函数 $f(P) = f(x, y)$ 的定义域为 $D$，$P_0 (x_0, y_0)$ 为 $D$ 的聚点，且 $P_0 \in D$。如果 $
\lim_{(x,y) \to (x_0, y_0)} f(x, y) = f(x_0, y_0),
$ 那么称函数 $f(x, y)$ 在点 $P_0 (x_0, y_0)$ 连续。  
>设函数 $f(x, y)$ 在 $D$ 上有定义，$D$ 内的每一点都是函数定义域的聚点。如果函数 $f(x, y)$ 在 $D$ 的每一点都连续，那么就称函数 $f(x, y)$ 在 $D$ 上连续，或者称 $f(x, y)$ 是 $D$ 上的连续函数。
>
> **$\lim_{x\rightarrow x_0, y\rightarrow y_0}$ $f(x, y) = f(x_0, y_0).$**
> 
>==间断点==
>设函数 $f(x,y)$ 的定义域为 $D$，$P_0(x_0, y_0)$ 是 $D$ 的聚点。如果函数 $f(x,y)$ 在点 $P_0(x_0, y_0)$ 不连续，那么称 $P_0(x_0, y_0)$ 为函数 $f(x,y)$ 的间断点。

> [!important]
>
> ==介值定理与最大最小值定理==
>
> **多元连续函数的性质**  
> 与闭区间上一元连续函数的性质相类似，在有界闭区域上连续的多元函数具有如下性质：
>
> >**性质1（有界性与最大值最小值定理）**  
> 在有界闭区域 $D$ 上的多元连续函数，必定在 $D$ 上有界，且能取得它的最大值和最小值。  
> 具体表述为：若 $f(P)$ 在有界闭区域 $D$ 上连续，则存在常数 $M > 0$，使得对一切 $P \in D$，有 $|f(P)| \leq M$；且存在 $P_1, P_2 \in D$，使得  
> $$
> f(P_1) = \max \{ f(P) \mid P \in D \}, \quad f(P_2) = \min \{ f(P) \mid P \in D \}
> $$
>
> >**性质2（介值定理）**  
> 在有界闭区域 $D$ 上的多元连续函数必取得介于最大值和最小值之间的任何值。
>
> >**性质3（一致连续性定理）**  
> 在有界闭区域 $D$ 上的多元连续函数必定在 $D$ 上一致连续。  
> 具体表述为：若 $f(P)$ 在 $D$ 上连续，则对于任意给定的 $\varepsilon > 0$，存在 $\delta > 0$，使得对于任意 $P_1, P_2 \in D$，当 $|P_1P_2| < \delta$ 时，有  
>
> $$
> |f(P_1) - f(P_2)| < \varepsilon
> $$


## 偏导数
> [!tip]
> ==偏导数==
> 设函数 $z=f(x,y)$ 在点 $(x_0,y_0)$ 的某一邻域内有定义，当 $y$ 固定在 $y_0$ 而 $x$ 在 $x_0$ 处有增量 $\Delta x$ 时，相应的函数增量为  
> $$ f(x_0 + \Delta x, y_0) - f(x_0, y_0) $$  
> 若极限  
> $$ \lim_{\Delta x \to 0} \frac{f(x_0 + \Delta x, y_0) - f(x_0, y_0)}{\Delta x} \tag{2-1} $$  
> 存在，则称此极限为函数 $z=f(x,y)$ 在点 $(x_0,y_0)$ 处对 $x$ 的**偏导数**，记作：  
> $$ \left. \frac{\partial z}{\partial x} \right|_{x=x_0}, \quad \left. \frac{\partial f}{\partial x} \right|_{x=x_0}, \quad z_x \bigg|_{x=x_0} \text{ 或 } f_x(x_0, y_0) \tag{1} $$
> >**示例表达式**  
> 极限 $(2-1)$ 可表示为：  
> $$ f_x(x_0, y_0) = \lim_{\Delta x \to 0} \frac{f(x_0 + \Delta x, y_0) - f(x_0, y_0)}{\Delta x} \tag{2-2} $$ 
> 类似地，定义对 $y$ 的偏导数为：  
> $$ \lim_{\Delta y \to 0} \frac{f(x_0, y_0 + \Delta y) - f(x_0, y_0)}{\Delta y} \tag{2-3} $$  
> 记作：  
> $$ \left. \frac{\partial z}{\partial y} \right|_{y=y_0}, \quad \left. \frac{\partial f}{\partial y} \right|_{y=y_0}, \quad z_y \bigg|_{y=y_0} \text{ 或 } f_y(x_0, y_0) $$
> >**偏导函数** ： 若 $z=f(x,y)$ 在区域 $D$ 内每一点 $(x,y)$ 处对 $x$ 的偏导数存在，则称此偏导数为**偏导函数**，记作：  
> $$ \frac{\partial z}{\partial x}, \quad \frac{\partial f}{\partial x}, \quad z_x \text{ 或 } f_x(x, y) $$  
> 对 $y$ 的偏导函数记为：  
> $$ \frac{\partial z}{\partial y}, \quad \frac{\partial f}{\partial y}, \quad z_y \text{ 或 } f_y(x, y) $$
> **首先固定其它变量, 看一个变量变化对函数值的影响.**

>**例1**. > 给定分段函数：
> $$
> z = f(x, y) = 
> \begin{cases} 
> \frac{xy}{x^2 + y^2}, & x^2 + y^2 \neq 0 \\
> 0, & x^2 + y^2 = 0 
> \end{cases}
> $$
>求函数在点 (0,0) 处的偏导数 $f_x(0, 0)$ 和 $f_y(0, 0)$.
> >**解** 
> **计算 $f_x(0, 0)$**  
> 根据偏导数定义：$ f_x(0, 0) = \lim_{\Delta x \to 0} \frac{f(0+\Delta x, 0) - f(0, 0)}{\Delta x} = \lim_{\Delta x \to 0} \frac{0 - 0}{\Delta x} = 0$
> **计算 $f_y(0, 0)$**  
> 同理：$f_y(0, 0) = \lim_{\Delta y \to 0} \frac{f(0, 0+\Delta y) - f(0, 0)}{\Delta y} = \lim_{\Delta y \to 0} \frac{0 - 0}{\Delta y} = 0$
>即$ f_x(0, 0) = 0, \quad f_y(0, 0) = 0 $

>**==高阶偏导数==**
> 设函数 $z = f(x, y)$ 在区域 $D$ 内具有偏导数
> $$ \frac{\partial z}{\partial x} = f_x(x, y), \quad \frac{\partial z}{\partial y} = f_y(x, y) $$
> 则在 $D$ 内 $f_x(x, y)$ 和 $f_y(x, y)$ 都是 $x, y$ 的函数。若这两个函数的偏导数也存在，则称它们是 $z = f(x, y)$ 的**二阶偏导数**。
> **二阶偏导数的四种形式**：
> 1. 对 $x$ 的二阶偏导：
> $$ \frac{\partial}{\partial x} \left( \frac{\partial z}{\partial x} \right) = \frac{\partial^2 z}{\partial x^2} = f_{xx}(x, y) $$
> 
> 2. 先对 $x$ 后对 $y$ 的混合偏导：
> $$ \frac{\partial}{\partial y} \left( \frac{\partial z}{\partial x} \right) = \frac{\partial^2 z}{\partial x \partial y} = f_{xy}(x, y) $$
> 
> 3. 先对 $y$ 后对 $x$ 的混合偏导：
> $$ \frac{\partial}{\partial x} \left( \frac{\partial z}{\partial y} \right) = \frac{\partial^2 z}{\partial y \partial x} = f_{yx}(x, y) $$
> 
> 4. 对 $y$ 的二阶偏导：
> $$ \frac{\partial}{\partial y} \left( \frac{\partial z}{\partial y} \right) = \frac{\partial^2 z}{\partial y^2} = f_{yy}(x, y) $$

>**例**. 设函数 $z = x^3 y^2 - 3xy^3 - xy + 1$，求下列高阶偏导数：
> $$ \frac{\partial^2 z}{\partial x^2},\ \frac{\partial^2 z}{\partial y \partial x},\ \frac{\partial^2 z}{\partial x \partial y},\ \frac{\partial^2 z}{\partial y^2} \ \text{及}\ \frac{\partial^3 z}{\partial x^3} $$
> >**解**  
> 求一阶偏导数:
> $ \frac{\partial z}{\partial x} = 3x^2 y^2 - 3y^3 - y $
> $ \frac{\partial z}{\partial y} = 2x^3 y - 9xy^2 - x $
> 求二阶偏导数：
> $ \frac{\partial^2 z}{\partial x^2} = \frac{\partial}{\partial x}(3x^2 y^2 - 3y^3 - y) = 6xy^2 $
> $ \frac{\partial^2 z}{\partial y \partial x} = \frac{\partial}{\partial y}(3x^2 y^2 - 3y^3 - y) = 6x^2 y - 9y^2 - 1 $
> $ \frac{\partial^2 z}{\partial x \partial y} = \frac{\partial}{\partial x}(2x^3 y - 9xy^2 - x) = 6x^2 y - 9y^2 - 1 $
> $ \frac{\partial^2 z}{\partial y^2} = \frac{\partial}{\partial y}(2x^3 y - 9xy^2 - x) = 2x^3 - 18xy $
> 求三阶偏导数
> $ \frac{\partial^3 z}{\partial x^3} = \frac{\partial}{\partial x}(6xy^2) = 6y^2 $
> **结果验证**  
> 观察到混合偏导数相等：
> $$ \frac{\partial^2 z}{\partial y \partial x} = \frac{\partial^2 z}{\partial x \partial y} = 6x^2 y - 9y^2 - 1 $$
> 符合Schwarz定理（当二阶混合偏导数连续时，求导顺序可交换）

>[!important]
>==**二阶混合偏导数定理**==  
> 如果函数 $z = f(x, y)$ 的两个二阶混合偏导数  $ \frac{\partial^2 z}{\partial y \partial x} \quad \text{和} \quad \frac{\partial^2 z}{\partial x \partial y} $  
> 在区域 $D$ 内连续，那么在该区域内必有： $ \frac{\partial^2 z}{\partial y \partial x} = \frac{\partial^2 z}{\partial x \partial y} $
> 即：**二阶混合偏导数在连续条件下与求导次序无关**。  

> **例1**  
> 验证函数 $z = \ln \sqrt{x^2 + y^2}$ 满足 ==**拉普拉斯方程**== ：
> $$ \frac{\partial^2 z}{\partial x^2} + \frac{\partial^2 z}{\partial y^2} = 0 $$
> >**证**   
> 首先将函数化简为：
> $$ z = \frac{1}{2} \ln(x^2 + y^2) $$  
>  $$ \frac{\partial z}{\partial x} = \frac{x}{x^2 + y^2} $$
>  $$ \frac{\partial z}{\partial y} = \frac{y}{x^2 + y^2} $$
>  $$ \frac{\partial^2 z}{\partial x^2} = \frac{y^2 - x^2}{(x^2 + y^2)^2} $$
>  $$ \frac{\partial^2 z}{\partial y^2} = \frac{x^2 - y^2}{(x^2 + y^2)^2} $$
> 验证方程 
> 将二阶偏导数相加：
> $$ \frac{\partial^2 z}{\partial x^2} + \frac{\partial^2 z}{\partial y^2} = \frac{y^2 - x^2 + x^2 - y^2}{(x^2 + y^2)^2} = 0 $$
>
> ---

> **例8**  
> 证明函数 $u = \dfrac{1}{r}$ 满足==拉普拉斯方程==：
> $$ \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} + \frac{\partial^2 u}{\partial z^2} = 0 $$
> 其中 $r = \sqrt{x^2 + y^2 + z^2}$。
> >**证明**  
>   $$ \frac{\partial u}{\partial x} = -\frac{1}{r^2} \cdot \frac{\partial r}{\partial x} = -\frac{x}{r^3} $$
>   $$ \frac{\partial^2 u}{\partial x^2} = -\frac{1}{r^3} + \frac{3x^2}{r^5} $$
>   由对称性可得：
>   $$ \frac{\partial^2 u}{\partial y^2} = -\frac{1}{r^3} + \frac{3y^2}{r^5}, \quad \frac{\partial^2 u}{\partial z^2} = -\frac{1}{r^3} + \frac{3z^2}{r^5} $$
>验证方程  
>   $$ \begin{aligned}
>   \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} + \frac{\partial^2 u}{\partial z^2} 
>   &= -\frac{3}{r^3} + \frac{3(x^2 + y^2 + z^2)}{r^5} \\
>   &= -\frac{3}{r^3} + \frac{3r^2}{r^5} \\
>   &= 0 \end{aligned} $$

## 全微分
> [!tip]
> 在学习全微分的知识之前，我们来回顾一下**一元函数微分**
> **定义**：对于函数 $y=f(x)$，若增量 $\Delta y$ 可表示为  
> $$\Delta y = A\Delta x + o(\Delta x)$$  
> 则称 $f(x)$ 在点 $x_0$ 可微，$A\Delta x$ 称为**微分**，记作 $dy = f'(x_0)dx$
>
> 那请你思考：如何将微分概念推广到 $z=f(x,y)$呢？
> >**第一层：代数理解**
>==**核心公式**==
>$$ dz = \frac{\partial z}{\partial x}dx + \frac{\partial z}{\partial y}dy $$
> **结构分解**：函数值如何随各个自变量的变化而变化.
> >- $\frac{\partial z}{\partial x}$：$x$方向的变化率
> >- $\frac{\partial z}{\partial y}$：$y$方向的变化率
> >- $dx, dy$：自变量的微小变化量


>[!important]
>**定义**：若函数 $z=f(x,y)$ 在点 $(x_0,y_0)$ 的全增量  
$$\Delta z = f(x_0+\Delta x,y_0+\Delta y)-f(x_0,y_0)$$  
可表示为：  
$$\Delta z = A\Delta x + B\Delta y + o(\rho)$$  
其中 $\rho=\sqrt{(\Delta x)^2+(\Delta y)^2}$，则称：
>- $f(x,y)$ 在 $(x_0,y_0)$ **可微**
>- $dz = A\Delta x + B\Delta y$ 称为 ==**全微分**==
>若函数在区域 $D$ 内各点处均可微分，则称该函数在 $D$ 内 ==**可微分**==。

> ==**函数可微分的条件**==
> 下面讨论函数 $z=f(x,y)$ 在点 $(x,y)$ 可微分的条件。
> ==**定理1（必要条件）**==  
> 如果函数 $z=f(x,y)$ 在点 $(x,y)$ 可微分，那么：
> 1. 该函数在点 $(x,y)$ 的偏导数 $\frac{\partial z}{\partial x}$ 和 $\frac{\partial z}{\partial y}$ 必定存在
> 2. 函数在点 $(x,y)$ 的全微分为
> $$ dz = \frac{\partial z}{\partial x} \Delta x + \frac{\partial z}{\partial y} \Delta y \tag{3-1} $$
> >**证明**  
> 设函数 $z=f(x,y)$ 在点 $P(x,y)$ 可微分。根据微分定义，对于点 $P$ 的某个邻域内的任意一点 $P'(x+\Delta x, y+\Delta y)$，有：
> $$ f(x+\Delta x, y+\Delta y)-f(x,y) = A\Delta x + B\Delta y + o(\rho) \quad \text{(3-2)} $$
> 其中 $\rho = \sqrt{(\Delta x)^2 + (\Delta y)^2}$。
> 取 $\Delta y=0$ 时  
> 此时 $\rho=|\Delta x|$，(3-2) 式变为：
> $$ f(x+\Delta x, y)-f(x,y) = A\Delta x + o(|\Delta x|) $$
> 两边除以 $\Delta x$ 并取极限：
> $$ \lim_{\Delta x\to 0}\frac{f(x+\Delta x, y)-f(x,y)}{\Delta x} = A $$
> 由此可得 $\frac{\partial z}{\partial x} = A$。
> 同理可证  
> 取 $\Delta x=0$ 可证得 $\frac{\partial z}{\partial y} = B$。
> 因此全微分表达式 (3-1) 得证。
>
> ==**偏导数存在仅为全微分存在的必要条件**==
> ==**反例**==  
> 考察函数：
> $$ f(x,y) = 
> \begin{cases} 
> \frac{xy}{\sqrt{x^2+y^2}}, & x^2+y^2 \neq 0 \\
> 0, & x^2+y^2=0 
> \end{cases} $$
> 
> >**证**：
>  在点 $(0,0)$ 处：
>    $$ f_x(0,0)=0,\quad f_y(0,0)=0 $$
>  计算增量差：
>    $$ \Delta z - [f_x(0,0)\Delta x + f_y(0,0)\Delta y] = \frac{\Delta x \Delta y}{\sqrt{(\Delta x)^2+(\Delta y)^2}} $$
>  沿直线 $y=x$ 趋近时：
>    $$ \frac{\Delta x \Delta y}{(\Delta x)^2+(\Delta y)^2} \bigg|_{y=x} = \frac{(\Delta x)^2}{2(\Delta x)^2} = \frac{1}{2} \nrightarrow 0 $$
> **结论**  
> 当 $\rho \to 0$ 时，$\Delta z - [f_x\Delta x + f_y\Delta y]$ 不是$\rho$的高阶无穷小，因此：$\text{函数在}(0,0)\text{处不可微分}$

> ---
>==**定理2（充分条件）**==
> 如果函数 $z=f(x,y)$ 的偏导数 $\frac{\partial z}{\partial x}$ 和 $\frac{\partial z}{\partial y}$ 在点 $(x,y)$ 连续，那么函数在该点可微分。
> >**证明**   
> 设偏导数 $\frac{\partial z}{\partial x}$ 和 $\frac{\partial z}{\partial y}$ 在点 $P(x,y)$ 的某邻域内存在且连续。
> 对邻域内任意点 $(x+\Delta x, y+\Delta y)$，全增量可分解为：
> $$ \Delta z = [f(x+\Delta x, y+\Delta y) - f(x,y+\Delta y)] + [f(x,y+\Delta y) - f(x,y)] $$
> 应用拉格朗日中值定理：
> $$ f(x+\Delta x, y+\Delta y) - f(x,y+\Delta y) = f_x(x+\theta_1\Delta x, y+\Delta y)\Delta x \quad (0<\theta_1<1) $$
> $$ = f_x(x,y)\Delta x + \varepsilon_1\Delta x \quad \text{(3-4)} $$
> 其中 $\lim_{(\Delta x,\Delta y)\to(0,0)} \varepsilon_1 = 0$
> 同理可得：
> $$ f(x,y+\Delta y) - f(x,y) = f_y(x,y)\Delta y + \varepsilon_2\Delta y \quad \text{(3-5)} $$
> 其中 $\lim_{\Delta y\to 0} \varepsilon_2 = 0$
> 综合得：
> $$ \Delta z = f_x(x,y)\Delta x + f_y(x,y)\Delta y + \varepsilon_1\Delta x + \varepsilon_2\Delta y \quad \text{(3-6)} $$ 
> 由于：
> $$ \left| \frac{\varepsilon_1\Delta x + \varepsilon_2\Delta y}{\rho} \right| \leq |\varepsilon_1| + |\varepsilon_2| \to 0 $$
> 当 $\rho = \sqrt{(\Delta x)^2 + (\Delta y)^2} \to 0$ 时，因此函数在 $P(x,y)$ 可微分。

> ---

>**例1**.$ z(x,y) = x + y $
> >**解:**
>变量变化：$x \to x + \Delta x, \quad y \to y + \Delta y$
>函数增量计算： $z(x + \Delta x, y + \Delta y) = (x + \Delta x) + (y + \Delta y)$
> 增量分解： $\Delta z = z(x + \Delta x, y + \Delta y) - z(x, y) = \Delta x + \Delta y$
>偏导数表示：  $\frac{\partial z}{\partial x} = 1, \quad \frac{\partial z}{\partial y} = 1$
>全微分公式：  $dz = dx + dy$

>**例2**.函数 $z(x,y) = x^2 + 2y^3$
> >**解：** 
考虑自变量的微小变化：
> $
> \begin{cases}
> x \rightarrow x + dx \\ 
> y \rightarrow y + dy
> \end{cases}
> $
>函数增量计算： $\begin{aligned}
> z(x+dx,y+dy) &= (x+dx)^2 + 2(y+dy)^3 \\
> &= x^2 + 2xdx + dx^2 + 2(y^3 + 3y^2dy + 3ydy^2 + dy^3) \\
> &= x^2 + 2y^3 + 2xdx + 6y^2dy + \underbrace{dx^2 + 6ydy^2 + 2dy^3}_{\text{高阶无穷小项}}
> \end{aligned} $
> 线性主部提取： 保留一阶增量项
> $
> \Delta z \approx 2xdx + 6y^2dy
> $
> 偏导数计算：
> $
> \frac{\partial z}{\partial x} = 2x \quad \text{和} \quad \frac{\partial z}{\partial y} = 6y^2
> $
> 全微分公式：$
> dz = \frac{\partial z}{\partial x}dx + \frac{\partial z}{\partial y}dy = 2xdx + 6y^2dy
> $

>**例3.** $ S = \frac{1}{2} \left( L - 2x + L - 2x + 2x \cos \theta \right) x \sin \theta $
> >**解:**化简：$ S(x, \theta) = L x \sin \theta - 2x^2 \sin \theta + x^2 \sin \theta \cos \theta $
> 变量代换过程：$ x \to x + \Delta x, \quad \theta \to \theta + \Delta \theta $
> 函数增量展开：
> $ 
> \begin{aligned}
> S(x+\Delta x, \theta+\Delta \theta) &= L (x+\Delta x) \sin(\theta+\Delta \theta) \\
> &\quad -2(x+\Delta x)^2 \sin(\theta+\Delta \theta) \\
> &\quad + (x+\Delta x)^2 \sin(\theta+\Delta \theta)\cos(\theta+\Delta \theta)
> \end{aligned}
> $
> 线性近似处理（保留一阶项）：
> $
> \begin{aligned}
> \Delta S &\approx (L \sin \theta - 4x \sin \theta + 2x \sin \theta \cos \theta)\Delta x \\
> &\quad + (L x \cos \theta - 2x^2 \cos \theta - x^2 \sin^2 \theta + x^2 \cos^2 \theta)\Delta \theta
> \end{aligned}$
> 偏导数提取：
> $
> \begin{cases}
> \frac{\partial S}{\partial x} = L \sin \theta - 4x \sin \theta + x \sin \theta \cos \theta \\
> \frac{\partial S}{\partial \theta} = L x \cos \theta - 2x^2 \cos \theta + x^2 (\cos^2 \theta - \sin^2 \theta)
> \end{cases}$
> 全微分公式：$dS = \frac{\partial S}{\partial x}dx + \frac{\partial S}{\partial \theta}d\theta$
> 最终结果：$dS = \sin\theta (L - 4x + 2x \cos\theta)dx + [x \cos\theta (L - 2x) + x^2 \cos 2\theta]d\theta$

> >**第二层：几何理解**
![全微分几何图示](media/img/Total_differential.jpg)
> 向量 $\overrightarrow{OA}$ 表示沿 $x$ 方向的变化：
   $
   \overrightarrow{OA} = \begin{pmatrix} 
   \Delta x \\ 
   0 \\ 
   \frac{\partial f}{\partial x} \Delta x 
   \end{pmatrix}
   $
> 向量 $\overrightarrow{OB}$ 表示沿 $y$ 方向的变化：
   $
   \overrightarrow{OB} = \begin{pmatrix} 
   0 \\ 
   \Delta y \\ 
   \frac{\partial f}{\partial y} \Delta y 
   \end{pmatrix}
   $
> 合成向量 $\overrightarrow{OC}$：
   $
   \overrightarrow{OC} = \overrightarrow{OA} + \overrightarrow{OB} = 
   \begin{pmatrix} 
   \Delta x \\ 
   \Delta y \\ 
   \frac{\partial f}{\partial x} \Delta x + \frac{\partial f}{\partial y} \Delta y 
   \end{pmatrix}
   $
>全微分关系
> 函数增量表达式：$
   f(x_0 + \Delta x, y_0 + \Delta y) = f(x_0, y_0) + \frac{\partial f}{\partial x} \Delta x + \frac{\partial f}{\partial y} \Delta y
   $
>增量与微分关系：$
   \Delta f = \frac{\partial f}{\partial x} \Delta x + \frac{\partial f}{\partial y} \Delta y
   $
>全微分形式：$
   df = \frac{\partial f}{\partial x} dx + \frac{\partial f}{\partial y} dy
   $
>几何解释
> 上述公式表明：**切平面**上的高度变化 $dz$ 是 $x$ 方向和 $y$ 方向变化的线性叠加。

> >**第三层：代数几何理解**
>全微分的代数与几何表示
>1、一元函数微分
>$
df = \frac{\partial f}{\partial x} \cdot dx = f' \cdot dx
$
$
f = f_0 + f' \cdot dx
$
>2、二元函数全微分
>$
df = \frac{\partial f}{\partial x} dx + \frac{\partial f}{\partial y} dy 
$
>$
= \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right)^T \cdot \left( dx, dy \right)^T
$
$
df = \vec{g} \cdot d\vec{x}
$
> 3、三元函数扩展
$
df = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z} \right)^T \cdot \left( dx, dy, dz \right)^T
$
$
= \frac{\partial f}{\partial x} dx + \frac{\partial f}{\partial y} dy + \frac{\partial f}{\partial z} dz
$
$
f = f_0 + \vec{g} \cdot d\vec{x}, \quad \vec{g} := \nabla f \text{（梯度）}
$
> **问题**：观察图片，函数在哪个方向变化率最大？
>![图示](media/img/Gradient_Descent.png)
>**答案**：沿梯度方向 $\nabla f$ 变化率最大。

>**梯度下降法：** 体会“盲人下山”的感觉，更好的理解梯度下降法。
>**一维函数（单变量）**
> 梯度表示：
> $ \nabla f(x) = f'(x) $
> 
> 极值条件：
> 1. 必要条件：
> $ f'(x_0) = 0 $
> 2. 充分条件：
> - 若 $f''(x_0) > 0$ → 极小值
> - 若 $f''(x_0) < 0$ → 极大值
> 
>**二维函数（双变量）**
> 梯度表示：
> $ \nabla f(x,y) = \begin{pmatrix} \frac{\partial f}{\partial x} \\ \frac{\partial f}{\partial y} \end{pmatrix} $
> 
> 极值条件：
> 1. 必要条件： $ \nabla f(x_0,y_0) = \mathbf{0} $
>说明有初值依赖性，且极值点是局部邻域最小值
> 2. 充分条件：
> 计算Hessian矩阵：
> $ H = \begin{bmatrix} \frac{\partial^2 f}{\partial x^2} & \frac{\partial^2 f}{\partial x \partial y} \\ \frac{\partial^2 f}{\partial y \partial x} & \frac{\partial^2 f}{\partial y^2} \end{bmatrix} $
> - $det(H) > 0$ 且 $\frac{\partial^2 f}{\partial x^2} > 0$ → 极小值
> - $det(H) > 0$ 且 $\frac{\partial^2 f}{\partial x^2} < 0$ → 极大值
> - $det(H) < 0$ → 鞍点
> 
> **高维函数（n变量）**
> 梯度表示：
> $ \nabla f(\mathbf{x}) = \begin{pmatrix} \frac{\partial f}{\partial x_1} \\ \vdots \\ \frac{\partial f}{\partial x_n} \end{pmatrix} $
> 
> 极值条件：
> 1. 必要条件：$ \nabla f(\mathbf{x}_0) = \mathbf{0} $
> 2. 充分条件：
> - Hessian矩阵正定 → 极小值
> - Hessian矩阵负定 → 极大值
> - Hessian矩阵有正负特征值 → 鞍点
> 
> 通用性质
> 1. 梯度方向：函数在该方向变化率最大
> 2. 极值检测：
> - 一维：二阶导数测试
> - 多维：Hessian矩阵特征值分析
> 3. 鞍点现象：仅在高维出现
> 注：所有情况均假设函数在考察点处可微
>
>
### 多元复合函数求导的链式法则
>
>P115.例6[待补充]
>P114.例5[待补充]
>例. $f(x, y) = \sin(x^2 + y) + \cos(x + y^2)$
> $
> \begin{cases} 
> 2x \cos(x^2 + y) - \sin(x + y^2) = 0 \\ 
> \cos(x^2 + y) - 2y \sin(x + y^2) = 0 
> \end{cases}
> $
## 隐函数求导
> 
>[!tip]
> **复习：直接求导法**
> 给定隐函数方程：$ x + \cos y = xy $
>  两边对$x$求导: $ \frac{d}{dx}(x) + \frac{d}{dx}(\cos y) = \frac{d}{dx}(xy) $
>  逐项计算：$ 1 - \sin y \cdot y' = y + x y' $
>  解出$y'$：$ y' = \frac{1 - y}{\sin y + x} $
> **全微分法（更通用的方法）**
> 将方程改写为：$ F(x,y) = x + \cos y - xy = 0 $
> **求导原理**：
>  计算全微分：$ dF = \frac{\partial F}{\partial x}dx + \frac{\partial F}{\partial y}dy = 0 $
>  求出偏导数：$ \frac{\partial F}{\partial x} = 1 - y $ ,  $ \frac{\partial F}{\partial y} = -\sin y - x $
> 根据隐函数定理：$ \frac{dy}{dx} = -\frac{\frac{\partial F}{\partial x}}{\frac{\partial F}{\partial y}} = \frac{1 - y}{\sin y + x} $
>**两种方法对比**
> | 方法       | 优点               | 缺点               |
> |------------|--------------------|--------------------|
> | 直接求导法 | 步骤直观           | 需显式处理$y$的函数性 |
> | 全微分法   | 通用性强，适合多变量 | 需计算偏导数        |
>
>**==隐函数存在定理==**
> >- **隐函数存在定理1** 
> 设函数 $F(x,y)$ 满足：
> >1. 在点 $P(x_0, y_0)$ 的某邻域内有连续偏导数
> >2. $F(x_0, y_0) = 0$
> >3. $F_y(x_0, y_0) \neq 0$
> 则方程 $F(x,y)=0$ 在 $(x_0,y_0)$ 的某邻域内：
> >- **唯一确定**一个连续可导函数 $y=f(x)$
> >- 满足 $y_0 = f(x_0)$
> >- 其导数为：
> $$ \frac{dy}{dx} = -\frac{F_x}{F_y} $$
> >- **隐函数存在定理2**  
> >设函数 $F(x,y,z)$ 满足：
> >1. 在点 $P(x_0,y_0,z_0)$ 的某邻域内有连续偏导数
> >2. $F(x_0,y_0,z_0) = 0$
> >3. $F_z(x_0,y_0,z_0) \neq 0$
>
> >则方程 $F(x,y,z)=0$ 在 $(x_0,y_0,z_0)$ 的某邻域内：
> >- **唯一确定**一个连续可微函数 $z=f(x,y)$
> >- 满足 $z_0 = f(x_0,y_0)$
> >- 其偏导数为：
> $$ \frac{\partial z}{\partial x} = -\frac{F_x}{F_z}, \quad \frac{\partial z}{\partial y} = -\frac{F_y}{F_z} \tag{5-4} $$
> **公式推导**  
> 由 $F(x,y,f(x,y)) \equiv 0$ 两边求导：
> 1. 对 $x$ 求导：$ F_x + F_z \frac{\partial z}{\partial x} = 0 \ \Rightarrow\ \frac{\partial z}{\partial x} = -\frac{F_x}{F_z} $
> 2. 对 $y$ 求导：$ F_y + F_z \frac{\partial z}{\partial y} = 0 \ \Rightarrow\ \frac{\partial z}{\partial y} = -\frac{F_y}{F_z} $
>

>**例1.** 给定隐函数方程：
> $F(x, y, z) = 0 $，（也可以成 $z = z(x, y)$） 求以下两个偏导数：$ \frac{\partial z}{\partial x} $,$ \frac{\partial z}{\partial y} $
> >**解：**
>  对$x$求偏导： $ \frac{\partial F}{\partial x} + \frac{\partial F}{\partial z} \frac{\partial z}{\partial x} = 0 $
>  对$y$求偏导： $ \frac{\partial F}{\partial y} + \frac{\partial F}{\partial z} \frac{\partial z}{\partial y} = 0 $
> 最终公式: $ \frac{\partial z}{\partial x} = -\frac{\frac{\partial F}{\partial x}}{\frac{\partial F}{\partial z}} $ ， $ \frac{\partial z}{\partial y} = -\frac{\frac{\partial F}{\partial y}}{\frac{\partial F}{\partial z}} $
> 
> >**记忆口诀**
> "交叉偏导，负号相连"
> >- 分子：非目标变量的偏导（如求$\frac{\partial z}{\partial x}$时分子是$\frac{\partial F}{\partial x}$）
> >- 分母：目标变量分母的偏导（总是$\frac{\partial F}{\partial z}$）

> **例2：** 给定隐函数方程：$ x^2 + y^2 + z^2 - 4z = 0 $，求 $ \frac{\partial^2 z}{\partial x^2}$
> >**解：**一阶偏导数计算：$ \frac{\partial z}{\partial x} = -\frac{x}{z-2} $
> 二阶偏导数推导：
>  对一阶导结果再次求导： $ \frac{\partial^2 z}{\partial x^2} = \frac{d}{dx}\left( -\frac{x}{z-2} \right) $
>应用商的导数法则：$ = -\frac{(1)(z-2) - x\frac{\partial z}{\partial x}}{(z-2)^2} $
> 代入$\frac{\partial z}{\partial x}$ 得$-\frac{(z-2) - x\left(-\frac{x}{z-2}\right)}{(z-2)^2} $ $ = \frac{2 - z - \frac{x^2}{z-2}}{(z-2)^2} $

>**例3.**
给定两个隐函数方程：
> $ 
> \begin{cases}
> P = F(x, y, u, v) = 0 \\
> q = Q(x, y, u, v) = 0 
> \end{cases}
> $  需要求解的偏导数矩阵：$ 
> \begin{pmatrix}
> \frac{\partial u}{\partial x} & \frac{\partial u}{\partial y} \\
> \frac{\partial v}{\partial x} & \frac{\partial v}{\partial y}
> \end{pmatrix}
> $
> >**解：**
> 对每个方程求全微分： $ 
> \begin{cases}
> dF = F_x dx + F_y dy + F_u du + F_v dv = 0 \\
> dG = G_x dx + G_y dy + G_u du + G_v dv = 0 
> \end{cases}
> $
> 整理成矩阵形式：
> $ 
> \begin{pmatrix}
> F_u & F_v \\
> G_u & G_v 
> \end{pmatrix}
> \begin{pmatrix}
> \frac{\partial u}{\partial x} \\
> \frac{\partial v}{\partial x}
> \end{pmatrix}
> = -
> \begin{pmatrix}
> F_x \\
> G_x 
> \end{pmatrix}
> $
> 解得：
> $
> \begin{pmatrix}
> \frac{\partial u}{\partial x} \\
> \frac{\partial v}{\partial x}
> \end{pmatrix}
> = -
> \begin{pmatrix}
> F_u & F_v \\
> G_u & G_v 
> \end{pmatrix}^{-1}
> \begin{pmatrix}
> F_x \\
> G_x 
> \end{pmatrix}
> $

>**例4**  $
> \begin{cases}
> xu - yv = 0 \\
> yu + xv = 1
> \end{cases}
> $ 求对函数 $u(x,y)$ 和 $v(x,y)$ 的偏导数$ u_x,u_y,v_x,v_y$
> >**解：**
> 第一个方程对$x$求导：$ u + x\frac{\partial u}{\partial x} - y\frac{\partial v}{\partial x} = 0 $
>  第二个方程对$x$求导：$y\frac{\partial u}{\partial x} + v + x\frac{\partial v}{\partial x} = 0 $
> 整理成方程组：$
> \begin{cases}
> xu_x - yv_x = -u \\
> yu_x + xv_x = -v
> \end{cases}
> $
>从第一式解出： $ u_x = \frac{yv_x - u}{x} $
> 代入第二式：$ y\left(\frac{yv_x - u}{x}\right) + v + xv_x = 0 $
> 化简得：$ (x^2 + y^2)v_x = yu - xv $
>最终解：$ v_x = \frac{yu - xv}{x^2 + y^2} $

>**例5**   给定约束方程组：[答案待补充]
> $ F = x - \rho\cos\theta = 0 $,
> $ G = y - \rho\sin\theta = 0 $

>**例6**
> 设 $u = f(x,y)$ 的所有二阶偏导数连续，将下列表达式转换为极坐标形式：  
> (1) $\left( \dfrac{\partial u}{\partial x} \right)^2 + \left( \dfrac{\partial u}{\partial y} \right)^2$  
> (2) $\dfrac{\partial^2 u}{\partial x^2} + \dfrac{\partial^2 u}{\partial y^2}$
> >**解**  
> 由极坐标关系 $\rho = \sqrt{x^2+y^2}$, $\theta = \arctan(y/x)$，通过链式法则：
> $$ \frac{\partial u}{\partial x} = \frac{\partial u}{\partial \rho}\cos\theta - \frac{\partial u}{\partial \theta}\frac{\sin\theta}{\rho} $$
> $$ \frac{\partial u}{\partial y} = \frac{\partial u}{\partial \rho}\sin\theta + \frac{\partial u}{\partial \theta}\frac{\cos\theta}{\rho} $$
> $$ \left(\frac{\partial u}{\partial x}\right)^2 + \left(\frac{\partial u}{\partial y}\right)^2 = \left(\frac{\partial u}{\partial \rho}\right)^2 + \frac{1}{\rho^2}\left(\frac{\partial u}{\partial \theta}\right)^2 $$
> $\frac{\partial^2 u}{\partial x^2}$展开：
> $$ \begin{aligned}
> \frac{\partial^2 u}{\partial x^2} &= \frac{\partial^2 u}{\partial \rho^2}\cos^2\theta - \frac{\partial^2 u}{\partial \rho \partial \theta}\sin 2\theta + \frac{\partial^2 u}{\partial \theta^2}\frac{\sin^2\theta}{\rho^2} \\
> &\quad + \frac{\partial u}{\partial \theta}\frac{\sin 2\theta}{\rho^2} + \frac{\partial u}{\partial \rho}\frac{\sin^2\theta}{\rho}
> \end{aligned} $$
> $\frac{\partial^2 u}{\partial y^2}$展开：
> $$ \begin{aligned}
> \frac{\partial^2 u}{\partial y^2} &= \frac{\partial^2 u}{\partial \rho^2}\sin^2\theta + \frac{\partial^2 u}{\partial \rho \partial \theta}\sin 2\theta + \frac{\partial^2 u}{\partial \theta^2}\frac{\cos^2\theta}{\rho^2} \\
> &\quad - \frac{\partial u}{\partial \theta}\frac{\sin 2\theta}{\rho^2} + \frac{\partial u}{\partial \rho}\frac{\cos^2\theta}{\rho}
> \end{aligned} $$
> 两式相加后化简得极坐标下的拉普拉斯算子：
> $$ \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = { \frac{\partial^2 u}{\partial \rho^2} + \frac{1}{\rho}\frac{\partial u}{\partial \rho} + \frac{1}{\rho^2}\frac{\partial^2 u}{\partial \theta^2} } $$
> >或等价表示为：
> $$ { \frac{1}{\rho}\frac{\partial}{\partial \rho}\left(\rho \frac{\partial u}{\partial \rho}\right) + \frac{1}{\rho^2}\frac{\partial^2 u}{\partial \theta^2} } $$


#### 几何应用
>
>**一、向量函数的导数**
[!tip]
> ==**一元向量值函数**==
> 设数集 $D \subseteq \mathbb{R}$，若映射：$ \mathbf{f}: D \to \mathbb{R}^n $
> 则称 $\mathbf{f}$ 为**一元向量值函数**，记作：$ \mathbf{r} = \mathbf{f}(t), \quad t \in D $
> - $D$：函数的定义域
> - $t$：自变量（标量）
> - $\mathbf{r}$：因变量（$n$维向量）
>
> ==**向量值函数的极限**==  
> 设向量值函数 $\mathbf{f}(t)$ 在点 $t_0$ 的某去心邻域内有定义。若存在常向量 $\mathbf{r}_0$ 满足：
> 
> $\forall \varepsilon > 0,\ \exists \delta > 0$，当 $0 < |t - t_0| < \delta$ 时，有
> $$ \|\mathbf{f}(t) - \mathbf{r}_0\| < \varepsilon $$
> 
> 则称 $\mathbf{r}_0$ 为 $\mathbf{f}(t)$ 当 $t \to t_0$ 时的**极限**，记作：$ \lim_{t \to t_0} \mathbf{f}(t) = \mathbf{r}_0 $ 或 $ \mathbf{f}(t) \to \mathbf{r}_0 \quad (t \to t_0) $
>

> **向量值函数导数的几何与物理意义**
> **几何解释**  
> 设空间曲线 $\Gamma$ 是向量值函数 $\mathbf{r} = \mathbf{f}(t)$ 的终端曲线，取点：
> - $M$: $\overrightarrow{OM} = \mathbf{f}(t_0)$  
> - $N$: $\overrightarrow{ON} = \mathbf{f}(t_0 + \Delta t)$  
> 
> 当 $\mathbf{f}'(t_0) \neq \mathbf{0}$ 时：
> 1. $\Delta t > 0$ 时，增量向量 $\Delta\mathbf{r} = \mathbf{f}(t_0+\Delta t) - \mathbf{f}(t_0)$ 与 $t$ 增长方向相同
> 2. $\Delta t < 0$ 时，$\Delta\mathbf{r}$ 与 $t$ 增长方向相反
> 3. **导数本质**：$\mathbf{f}'(t_0) = \lim\limits_{\Delta t \to 0} \frac{\Delta\mathbf{r}}{\Delta t}$ 始终指向 $t$ 增长方向，是曲线 $\Gamma$ 在 $M$ 点的**切向量**

> **物理意义（质点运动）**  
> 若 $\mathbf{r} = \mathbf{f}(t)$ 表示运动质点的位置向量：
> - **速度向量**：  
>   $$ \mathbf{v}(t) = \frac{d\mathbf{r}}{dt} $$  
>   方向沿曲线切线方向
> - **加速度向量**：  
>   $$ \mathbf{a}(t) = \frac{d\mathbf{v}}{dt} = \frac{d^2\mathbf{r}}{dt^2} $$  
>   描述速度变化率
>
> ![图9-7 向量导数的几何示意](media/img/curve_tangent_vector.png "终端曲线与切向量")

>**分量形式表示**
> 向量函数对参数的导数：
> $$ \frac{d\vec{x}(t)}{dt} = \begin{pmatrix} \frac{dx(t)}{dt} \\ \frac{dy(t)}{dt} \\ \frac{dz(t)}{dt} \end{pmatrix} $$
> ![free_fall](media/img/free_fall.png)
>**运动学示例**
> 1. 位置向量：
> $$ \vec{x}(t) = \begin{pmatrix} V_0 t \\ \frac{1}{2}gt^2 \end{pmatrix} $$
> 
> 2. 速度向量（一阶导）：
> $$ \dot{\vec{x}}(t) = \begin{pmatrix} V_0 \\ gt \end{pmatrix} $$
> 
> 3. 加速度向量（二阶导）：
> $$ \ddot{\vec{x}}(t) = \begin{pmatrix} 0 \\ g \end{pmatrix} $$


>**二、几何形式**
>[!tip]
>匀速圆周运动的几何分析
>![匀速圆周运动](media/img/Uniform_circular_motiont.jpg)
> **向心加速度推导**
> 加速度大小：$ a = \omega^2 R $，方向始终指向圆心

> **三、运动学关系**[这里没看懂在写什么，待补充]
>[!tip]
> **速度与加速度**  
>  速度向量：$ \dot{\gamma}(t) = \frac{d\vec{r}}{dt} = \vec{v}(t) $
>  加速度向量：$ \ddot{\gamma}(t) = \frac{d^2\vec{r}}{dt^2} = \vec{a}(t) $
> **单位向量分解**  
> 速度的单位向量表示：$ \dot{\gamma}(t) = \dot{\gamma}(t) \cdot \hat{\gamma}(t) $
> 其中 $\hat{\gamma}(t)$ 为单位方向向量
>位置向量的微分：$ \frac{d\vec{r}(t)}{dt} = \frac{d\gamma(t)}{dt} \cdot \hat{\gamma}(t) + \gamma(t)\frac{d\hat{\gamma}(t)}{dt} $
> **极坐标表示**  
> 单位向量的微分：$ \frac{d\hat{\gamma}(t)}{dt} = \dot{\gamma}\hat{\theta} + \gamma\dot{\theta}(-\hat{\gamma}) $
> 极坐标参数：$ (\gamma, \theta) $
>  微分关系： $ d\hat{\gamma} = \gamma\dot{\theta}\hat{\theta} $
>  向量恒等式：$ \hat{\gamma} \times \hat{\theta} = -\hat{\gamma} \cdot \gamma\dot{\theta} \cdot \hat{\theta} $
> ![一般运动](media/img/general_motion.png)

>
>**例1**  
>设向量值函数：$ \mathbf{f}(t) = (\cos t)\mathbf{i} + (\sin t)\mathbf{j} + t\mathbf{k} $ , 求极限 $\lim\limits_{t \to \frac{\pi}{4}} \mathbf{f}(t)$.
>>**解**  
>分量式求极限：
>
>$$
>\begin{aligned}
>\lim_{t \to \frac{\pi}{4}} \mathbf{f}(t) &= \left( \lim_{t \to \frac{\pi}{4}} \cos t \right)\mathbf{i} + \left( \lim_{t \to \frac{\pi}{4}} \sin t \right)\mathbf{j} + \left( \lim_{t \to \frac{\pi}{4}} t \right)\mathbf{k} \\
>&= \frac{\sqrt{2}}{2}\mathbf{i} + \frac{\sqrt{2}}{2}\mathbf{j} + \frac{\pi}{4}\mathbf{k}
>\end{aligned}
>$$

> **例2**. 设空间曲线 $\Gamma$ 的向量方程为
> $$ r = f(t) = (t^2 + 1, 4t - 3, 2t^2 - 6t), t \in \mathbb{R}, $$
> 求曲线 $\Gamma$ 在与 $t = 2$ 相应的点处的单位切向量。
> >**解** 
> $$ f'(t) = (2t, 4, 4t - 6), t \in \mathbb{R}, $$ 
> $$ f'(2) = (4, 4, 2), $$ 
> $$ |f'(2)| = \sqrt{4^2 + 4^2 + 2^2} = 6. $$
> 由导向量的几何意义知，曲线 $\Gamma$ 在与 $t = 2$ 相应的点处的一个单位切向量是 $\left( \frac{2}{3}, \frac{2}{3}, \frac{1}{3} \right)$，其指向与 $t$ 的增长方向一致；另一个单位切向量是 $\left( -\frac{2}{3}, -\frac{2}{3}, -\frac{1}{3} \right)$，其指向与 $t$ 的增长方向相反。

> **例3**. 一个人在悬挂式滑翔机上由于快速上升气流而沿位置向量为 $r = f(t) = (3\cos t)i + (3\sin t)j + t^2k$ 的路径螺旋式向上。求
> （1）滑翔机在任意时刻 $t$ 的速度向量和加速度向量；
> （2）滑翔机在任意时刻 $t$ 的速率；
> （3）滑翔机的加速度与速度正交的时刻。
> >**解** 
> （1） 
> $$ r = f(t) = (3\cos t)i + (3\sin t)j + t^2k, $$ 
> $$ v = \frac{dr}{dt} = (-3\sin t)i + (3\cos t)j + 2tk, $$ 
> $$ a = \frac{d^2r}{dt^2} = (-3\cos t)i - (3\sin t)j + 2k. $$
> （2）速率是速度的大小，即 
> $$ |v| = \sqrt{(-3\sin t)^2 + (3\cos t)^2 + (2t)^2} = \sqrt{9 + 4t^2}. $$
> 这一结果表明：滑翔机沿其路径升高时，运动得越来越快。
> （3）由 $v \cdot a = 9\sin t \cos t - 9\sin t \cos t + 4t = 0$，得 $t = 0$。这表明：加速度与速度正交的唯一时刻是在 $t = 0$。
### 空间曲线的切线与法平面
>==参数曲线定义==
> 设空间曲线 $\Gamma$ 的参数方程为：
> $$
> \begin{cases} 
> x = \varphi(t) \\ 
> y = \psi(t) \quad t \in [\alpha, \beta] \\ 
> z = \omega(t) 
> \end{cases} 
> $$
> 其中 $\varphi(t), \psi(t), \omega(t)$ 在 $[\alpha, \beta]$ 上可导且导数不同时为零。
> ==切向量与切线方程==
> 对于曲线上点 $M(x_0,y_0,z_0)$（对应参数 $t_0$），定义向量值函数：
> $$ \mathbf{f}(t) = (\varphi(t), \psi(t), \omega(t)) $$
> ==切向量==：
> $$ \mathbf{T} = \mathbf{f}'(t_0) = (\varphi'(t_0), \psi'(t_0), \omega'(t_0)) $$
> ==切线方程==（对称式）：
> $$ { \frac{x-x_0}{\varphi'(t_0)} = \frac{y-y_0}{\psi'(t_0)} = \frac{z-z_0}{\omega'(t_0)} } $$
> ==法平面方程==
> 法平面是以 $\mathbf{T}$ 为法向量且通过 $M$ 点的平面：
> $$ { \varphi'(t_0)(x-x_0) + \psi'(t_0)(y-y_0) + \omega'(t_0)(z-z_0) = 0 }$$

> **例** 求曲线 $x^2 + y^2 + z^2 = 6$, $x + y + z = 0$ 在点 $(1, -2, 1)$ 处的切线及法平面方程。
> >**解** 将所给方程的两边对 $x$ 求导并移项，得
> $$
> \begin{cases}
> y \frac{dy}{dx} + z \frac{dz}{dx} = -x, \\
> \frac{dy}{dx} + \frac{dz}{dx} = -1.
> \end{cases}
> $$
> 由此得
> $$
> \frac{dy}{dx} = \frac{z - x}{y - z}, \quad \frac{dz}{dx} = \frac{x - y}{y - z}.
> $$
> 从而
> $$
> \frac{dy}{dx} \bigg|_{(1,-2,1)} = 0, \quad \frac{dz}{dx} \bigg|_{(1,-2,1)} = -1.
> $$
> 故所求切线方程为
> $$
> \frac{x - 1}{1} = \frac{y + 2}{0} = \frac{z - 1}{-1},
> $$
> 法平面方程为
> $$
> (x - 1) + 0 \cdot (y + 2) - (z - 1) = 0,
> $$
> 即 $x - z = 0.$

### 曲面的切平面和法线
> **给定曲面**  
> 设曲面Σ的方程为 $F(x,y,z) = 0$，点 $M(x_0,y_0,z_0)$ 在曲面上
>==**法向量确定**==  
> 若 $F$ 在点 $M$ 处可微，且梯度 $\nabla F \neq \mathbf{0}$，则：
> $$\mathbf{n} = (F_x(x_0,y_0,z_0),\ F_y(x_0,y_0,z_0),\ F_z(x_0,y_0,z_0))$$
> ==**切平面方程**==  
> $${F_x(x_0,y_0,z_0)(x-x_0) + F_y(x_0,y_0,z_0)(y-y_0) + F_z(x_0,y_0,z_0)(z-z_0) = 0}$$
> ==**法线方程**==  
> $${\frac{x-x_0}{F_x(x_0,y_0,z_0)} = \frac{y-y_0}{F_y(x_0,y_0,z_0)} = \frac{z-z_0}{F_z(x_0,y_0,z_0)}}$$
> ==**显式曲面特殊情况**==  
> 当曲面为 $z=f(x,y)$ 时：
> - 法向量：$\mathbf{n} = (f_x(x_0,y_0),\ f_y(x_0,y_0),\ -1)$
> - 切平面方程：
> $${z-z_0 = f_x(x_0,y_0)(x-x_0) + f_y(x_0,y_0)(y-y_0)}$$

> **例1** 求球面 $x^2 + y^2 + z^2 = 14$ 在点 $(1,2,3)$ 处的切平面及法线方程。
> >**解**  :设 $F(x,y,z) = x^2 + y^2 + z^2 - 14$，则法向量：
> $$ \mathbf{n} = (F_x, F_y, F_z) = (2x, 2y, 2z) $$
> 在点 $(1,2,3)$ 处：
> $$ \mathbf{n}\big|_{(1,2,3)} = (2,4,6) $$
> **切平面方程**  
> $$ 2(x-1) + 4(y-2) + 6(z-3) = 0 $$
> 化简得：
> $$ {x + 2y + 3z - 14 = 0} $$
> **法线方程**  
> 对称式：
> $$ \frac{x-1}{1} = \frac{y-2}{2} = \frac{z-3}{3} $$
> 或等价表示为：
> $$ {\frac{x}{1} = \frac{y}{2} = \frac{z}{3}} $$
> *（法线通过原点/球心）*

>**例2**[P102,例7]

## 方向导数
>[!important]
> ==**方向导数的定义**==  
> 设函数 $f(x,y,z)$ 在点 $P_0(x_0,y_0,z_0)$ 的某邻域内有定义，$\mathbf{l}$ 为从 $P_0$ 出发的给定方向向量，$P(x,y,z)$ 为 $\mathbf{l}$ 上邻近 $P_0$ 的点。若极限  
> $$
> \lim_{\rho \to 0^+} \frac{f(P) - f(P_0)}{\rho} = \left. \frac{\partial f}{\partial l} \right|_{P_0}
> $$
> 存在，则称此极限为 $f$ 在 $P_0$ 点沿方向 $\mathbf{l}$ 的**方向导数**，其中 $\rho = |PP_0|$。
> ==**计算公式**==  
> 当 $f$ 在 $P_0$ 点可微时，方向导数可通过梯度计算：  
> $$
> \left. \frac{\partial f}{\partial l} \right|_{P_0} = \nabla f(P_0) \cdot \mathbf{l}^0 = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z} \right) \cdot (cos\alpha, cos\beta, cos\gamma)
> $$
> 其中 $\mathbf{l}^0 = (cos\alpha, cos\beta, cos\gamma)$ 为单位方向向量。
> ==**几何意义**==  
> 方向导数表示函数沿 $\mathbf{l}$ 方向的瞬时变化率：
> - 当 $\nabla f$ 与 $\mathbf{l}$ 同向时取最大值 $|\nabla f|$
> - 当 $\nabla f$ 与 $\mathbf{l}$ 反向时取最小值 $-|\nabla f|$
> - 当 $\nabla f \perp \mathbf{l}$ 时方向导数为零

>==**方向导数存在定理**==  
> 若函数 $f(x,y)$ 在点 $P_0(x_0,y_0)$ 可微分，则沿任一方向 $\mathbf{l}$ 的方向导数存在，且满足：
> $${ \left. \frac{\partial f}{\partial l} \right|_{(x_0,y_0)} = f_x(x_0,y_0)\cos\alpha + f_y(x_0,y_0)\cos\beta } $$
> 其中 $\cos\alpha$, $\cos\beta$ 为方向 $\mathbf{l}$ 的方向余弦。
> >**证明**  
> 由 $f(x,y)$ 在 $(x_0,y_0)$ 可微：
> $$
> \begin{aligned}
> &f(x_0+\Delta x, y_0+\Delta y) - f(x_0,y_0) \\
> &= f_x(x_0,y_0)\Delta x + f_y(x_0,y_0)\Delta y + o(\sqrt{(\Delta x)^2 + (\Delta y)^2})
> \end{aligned}
> $$
> 当 $(x_0+\Delta x, y_0+\Delta y)$ 在方向 $\mathbf{l}$ 上时：
> $$\Delta x = t\cos\alpha,\ \Delta y = t\cos\beta,\ \sqrt{(\Delta x)^2 + (\Delta y)^2} = t$$
> 因此：
> $$
> \begin{aligned}
> &\lim_{t \to 0^+} \frac{f(x_0 + t\cos\alpha, y_0 + t\cos\beta) - f(x_0,y_0)}{t} \\
> &= f_x(x_0,y_0)\cos\alpha + f_y(x_0,y_0)\cos\beta
> \end{aligned}
> $$
> 证得方向导数存在且等于原式。

>**例1** 求函数 \( z = xe^{2y} \) 在点 \( P(1,0) \) 沿 \( P \rightarrow Q(2,-1) \) 方向的方向导数。
> >**解**  
>   方向向量 \( \vec{PQ} = (1,-1) \)，单位化得：  
>   $$ \vec{n} = \frac{1}{\sqrt{2}}(1,-1)^T $$ 
>   - \( \left.\dfrac{\partial z}{\partial x}\right|_{(1,0)} = e^{2y}\big|_{(1,0)} = 1 \)  
>   - \( \left.\dfrac{\partial z}{\partial y}\right|_{(1,0)} = 2xe^{2y}\big|_{(1,0)} = 2 \)
>   $$
>   \left.\dfrac{\partial z}{\partial l}\right|_{(1,0)} = \nabla z \cdot \vec{n} = \frac{1}{\sqrt{2}} - \frac{2}{\sqrt{2}} = \boxed{ -\dfrac{1}{\sqrt{2}} }
>   $$

> **例2** 求函数 \( f(x,y,z) = xy + yz + zx \) 在点 \( (1,1,2) \) 沿方向 \( l \) 的方向导数，方向角为 \( 60^\circ, 45^\circ, 60^\circ \)。
> >**解**  
>   单位方向向量：
>   $$ \mathbf{e}_l = \left( \cos 60^\circ, \cos 45^\circ, \cos 60^\circ \right) = { \left( \frac{1}{2}, \frac{\sqrt{2}}{2}, \frac{1}{2} \right) } $$ 
>   $$
>   \begin{aligned}
>   f_x(1,1,2) &= (y+z)\big|_{(1,1,2)} = 3 \\
>   f_y(1,1,2) &= (x+z)\big|_{(1,1,2)} = 3 \\
>   f_z(1,1,2) &= (y+x)\big|_{(1,1,2)} = 2
>   \end{aligned}
>   $$
>   $$
>   \left. \frac{\partial f}{\partial l} \right|_{(1,1,2)} = 3 \cdot \frac{1}{2} + 3 \cdot \frac{\sqrt{2}}{2} + 2 \cdot \frac{1}{2} = { \frac{5 + 3\sqrt{2}}{2} }
>   $$
> **注**：计算中利用了方向导数公式：
> $$ \frac{\partial f}{\partial l} = \nabla f \cdot \mathbf{e}_l $$

### 梯度
> ==**梯度的定义**==
> 设二元函数 \( f(x,y) \) 在区域 \( D \) 内具有一阶连续偏导数，则对于任意点 \( P_0(x_0,y_0) \in D \)，其梯度定义为：
> $$
> \text{grad}\, f(x_0,y_0) = \nabla f(x_0,y_0) = f_x(x_0,y_0)\,\mathbf{i} + f_y(x_0,y_0)\,\mathbf{j}
> $$
> 其中微分算子 \( \nabla = \dfrac{\partial}{\partial x}\mathbf{i} + \dfrac{\partial}{\partial y}\mathbf{j} \)。
> ==**方向导数与梯度的关系**==  
> 当 \( f(x,y) \) 在 \( P_0 \) 可微时，沿单位方向 \( \mathbf{e}_l = (\cos\alpha,\cos\beta) \) 的方向导数为：
> $$
> \left. \frac{\partial f}{\partial l} \right|_{(x_0,y_0)} = \nabla f(x_0,y_0) \cdot \mathbf{e}_l = \|\nabla f(x_0,y_0)\| \cos\theta
> $$
> 其中 \( \theta \) 为梯度向量与方向 \( \mathbf{e}_l \) 的夹角。
> ==**梯度的几何特性**==  
> >1. **最大增长率方向**  
>   当 \( \theta=0 \)（方向与梯度同向）时：
>   $$
>   \left. \frac{\partial f}{\partial l} \right|_{(x_0,y_0)} = \|\nabla f(x_0,y_0)\|
>   $$
>   *此时函数增长最快，增长率等于梯度模长*
> >2. **最大减少率方向**  
>   当 \( \theta=\pi \)（方向与梯度反向）时：
>   $$
>   \left. \frac{\partial f}{\partial l} \right|_{(x_0,y_0)} = -\|\nabla f(x_0,y_0)\|
>   $$
>   *此时函数减少最快*
> >3. **零变化率方向**  
>   当 \( \theta=\dfrac{\pi}{2} \)（方向与梯度正交）时：
>   $$
>   \left. \frac{\partial f}{\partial l} \right|_{(x_0,y_0)} = 0
>   $$
>   *此时函数值不变化*

> **重要结论**  
> - 梯度方向是函数值增长最快的方向  
> - 梯度模长等于方向导数的最大值  
> - 等值线的法线方向与梯度方向一致

> **例3** 求 $\mathrm{grad}\ \dfrac{1}{x^2 + y^2}$： 
>
> >**解** 这里 $f(x, y) = \dfrac{1}{x^2 + y^2}$，因为 
> $$
> \frac{\partial f}{\partial x} = -\frac{2x}{(x^2 + y^2)^2}, \quad  
> \frac{\partial f}{\partial y} = -\frac{2y}{(x^2 + y^2)^2},
> $$
> 所以  
> $$
> \mathrm{grad}\ \dfrac{1}{x^2 + y^2} = -\frac{2x}{(x^2 + y^2)^2} \mathbf{i} - \frac{2y}{(x^2 + y^2)^2} \mathbf{j}.
> $$

> **例4** 设 $f(x, y) = \dfrac{1}{2}(x^2 + y^2),\ P_0(1,1)$，求  
> (1) $f(x, y)$ 在 $P_0$ 处增加最快的方向以及 $f(x, y)$ 沿这个方向的方向导数；  
> (2) $f(x, y)$ 在 $P_0$ 处减少最快的方向以及 $f(x, y)$ 沿这个方向的方向导数；  
> (3) $f(x, y)$ 在 $P_0$ 处的变化率为零的方向。  
> >**解** (1) $f(x, y)$ 在 $P_0$ 处沿 $\nabla f(1,1)$ 的方向增加最快，  
> $$
> \nabla f(1,1) = (x\mathbf{i} + y\mathbf{j})\Big|_{(1,1)} = \mathbf{i} + \mathbf{j},
> $$
> 故所求方向可取为  
> $$
> \mathbf{n} = \frac{\nabla f(1,1)}{|\nabla f(1,1)|} = \frac{1}{\sqrt{2}}\mathbf{i} + \frac{1}{\sqrt{2}}\mathbf{j},
> $$
> 方向导数为  
> $$
> \left. \frac{\partial f}{\partial \mathbf{n}} \right|_{(1,1)} = |\nabla f(1,1)| = \sqrt{2}.
> $$
> (2) $f(x, y)$ 在 $P_0$ 处沿 $-\nabla f(1,1)$ 的方向减少最快，这方向可取为  
> $$
> \mathbf{n}_1 = -\mathbf{n} = -\frac{1}{\sqrt{2}} \mathbf{i} - \frac{1}{\sqrt{2}} \mathbf{j},
> $$
> 方向导数为  
> $$
> \left. \frac{\partial f}{\partial \mathbf{n}_1} \right|_{(1,1)} = -|\nabla f(1,1)| = -\sqrt{2}.
> $$
> (3) $f(x, y)$ 在 $P_0$ 处沿垂直于 $\nabla f(1,1)$ 的方向变化率为零，这方向是  
> $$
> \mathbf{n}_2 = -\frac{1}{\sqrt{2}} \mathbf{i} + \frac{1}{\sqrt{2}} \mathbf{j} \quad \text{或} \quad \mathbf{n}_3 = \frac{1}{\sqrt{2}} \mathbf{i} - \frac{1}{\sqrt{2}} \mathbf{j}.
> $$

> **例5** 设 $f(x, y, z) = x^3 - x y^2 - z^2,\ P_0(1,1,0)$。问 $f(x,y,z)$ 在 $P_0$ 处沿什么方向变化最快，  在这个方向的变化率是多少？  
> >**解** $\nabla f = \dfrac{\partial f}{\partial x}\mathbf{i} + \dfrac{\partial f}{\partial y}\mathbf{j} + \dfrac{\partial f}{\partial z}\mathbf{k} = (3x^2 - y^2)\mathbf{i} - 2xy\mathbf{j} - 2z\mathbf{k},\ \nabla f(1,1,0) = 2\mathbf{i} - 2\mathbf{j} - \mathbf{k}$.  
> $f(x,y,z)$ 在 $P_0$ 处沿 $\nabla f(1,1,0)$ 的方向增加最快，沿 $-\nabla f(1,1,0)$ 的方向减少最快，在这两个方向的变化率分别是  
>
> $$
> |\nabla f(1,1,0)| = \sqrt{2^2 + (-2)^2 + 1^2} = 3, \quad -|\nabla f(1,1,0)| = -3.
> $$

> **例6** 求曲面 $x^2 + y^2 + z = 9$ 在点 $P_0(1,2,4)$ 的切平面和法线方程。  
> >**解** 设 $f(x, y, z) = x^2 + y^2 + z$，由梯度与等值面的关系可知，梯度  
> $$
> \nabla f \Big|_{P_0} = (2x\mathbf{i} + 2y\mathbf{j} + \mathbf{k})\Big|_{(1,2,4)} = 2\mathbf{i} + 4\mathbf{j} + \mathbf{k}
> $$
> 的方向是等值面 $f(x,y,z)=9$ 在点 $P_0$ 的法线方向，因此切平面方程是  
> $$
> 2(x - 1) + 4(y - 2) + (z - 4) = 0,
> $$
> 即  
> $$
> 2x + 4y + z = 14,
> $$
> 曲面在 $P_0$ 处的法线方程是  
> $$
> x = 1 + 2t,\ y = 2 + 4t,\ z = 4 + t \quad (t\ \text{为任意常数}).
> $$


> ==**三元函数的梯度定义与性质**==
> 设三元函数 \( f(x,y,z) \) 在空间区域 \( G \) 内具有一阶连续偏导数，则对于点 \( P_0(x_0,y_0,z_0) \in G \)，其梯度为：
> $$
> \text{grad}\, f(x_0,y_0,z_0) = \nabla f(x_0,y_0,z_0) = f_x\,\mathbf{i} + f_y\,\mathbf{j} + f_z\,\mathbf{k}
> $$
> 其中三维Nabla算子：
> $$ \nabla = \dfrac{\partial}{\partial x}\mathbf{i} + \dfrac{\partial}{\partial y}\mathbf{j} + \dfrac{\partial}{\partial z}\mathbf{k} $$
> ==**几何特性**==  
> >**方向极值性**  
>   - 梯度方向是函数值增长最快的方向  
>   - 梯度模长等于方向导数最大值：
>     $$ \|\nabla f\| = \max \left. \frac{\partial f}{\partial l} \right|_{P_0} $$
> >    **等值面法向性**  
>     对于等值面 \( f(x,y,z)=c \)，梯度方向与该点法线方向 \( \mathbf{n} \) 重合：
>     $$ \nabla f \parallel \mathbf{n} $$
>     且法线方向导数为：
>     $$ \left. \frac{\partial f}{\partial n} \right|_{P_0} = \|\nabla f\| $$
> >    **与二元函数梯度的一致性**  
>     三元函数梯度保留了二元函数梯度的所有核心性质：
> > >- 方向导数公式：
>   $$ \left. \frac{\partial f}{\partial l} \right|_{P_0} = \nabla f \cdot \mathbf{e}_l $$
> > >- 正交方向导数为零
> > >- 线性运算性质不变
>
> **例**  
> 对 \( f(x,y,z)=x^2+yz \) 在点 \( (1,2,3) \) 的梯度：
> $$ \nabla f = (2x, z, y) \big|_{(1,2,3)} = {(2,3,2)} $$

> ==**数量场与向量场的概念**==
> **定义**  
> - **数量场**：区域 $G$ 内每点 $M$ 对应确定数量 $f(M)$（如温度场、密度场）  
> - **向量场**：区域 $G$ 内每点 $M$ 对应向量 $\mathbf{F}(M) = P(M)\mathbf{i} + Q(M)\mathbf{j} + R(M)\mathbf{k}$（如力场、速度场）
> **势场与梯度场**  
> 若向量场 $\mathbf{F}(M)$ 是某数量场 $f(M)$ 的梯度，则称：  
> - $f(M)$ 为 $\mathbf{F}(M)$ 的**势函数**  
> - $\mathbf{F}(M)$ 为**势场**  
> *注：不是所有向量场都是势场*




> **例：引力势场的梯度**  
> 求数量场 $\dfrac{m}{r}$ 的梯度场（$m>0$, $r=\sqrt{x^2+y^2+z^2}$）：  
> >**解**  
>   $$
>   \frac{\partial}{\partial x}\left(\frac{m}{r}\right) = -\frac{mx}{r^3}, \quad
>   \frac{\partial}{\partial y}\left(\frac{m}{r}\right) = -\frac{my}{r^3}, \quad
>   \frac{\partial}{\partial z}\left(\frac{m}{r}\right) = -\frac{mz}{r^3}
>   $$
>   $$
>   \text{grad}\,\frac{m}{r} = -\frac{m}{r^2}\left(\frac{x}{r}\mathbf{i} + \frac{y}{r}\mathbf{j} + \frac{z}{r}\mathbf{k}\right) = -\frac{m}{r^2}\mathbf{e}_r
>   $$
>   其中 $\mathbf{e}_r = \dfrac{x}{r}\mathbf{i} + \dfrac{y}{r}\mathbf{j} + \dfrac{z}{r}\mathbf{k}$ 为径向单位向量

> **物理意义**  
> 该梯度场对应**引力场**：  
> - 大小：与质量 $m$ 成正比，与距离平方 $r^2$ 成反比  
> - 方向：指向原点 $O$  
> - 函数 $\dfrac{m}{r}$ 称为**引力势**

## 多元函数的极值及其求法

### 多元函数的极大值和极小值
>[!important]
> **定义** 若函数 $f(x, y)$ 在点 $(x_0, y_0)$ 的某邻域内有  
> $$
> f(x, y) \leq f(x_0, y_0)\quad (\text{或}\ f(x, y) \geq f(x_0, y_0)),
> $$
> 对所有在该邻域内的点 $(x, y)$ 都成立，则称 $f(x, y)$ 在点 $(x_0, y_0)$ 处有**极大值**（或**极小值**），$f(x_0, y_0)$ 称为**极大值**（或**极小值**）。  
>  
> 若 $f(x, y)$ 在点 $(x_0, y_0)$ 处有极大值或极小值，则称其在该点有**极值**。  
>  
> 若存在邻域内除了点 $(x_0, y_0)$ 本身外，  
> $$
> f(x, y) < f(x_0, y_0) \quad \text{和} \quad f(x, y) > f(x_0, y_0)
> $$
> 同时都能成立，则称 $f(x_0, y_0)$ 为**鞍点**。
>**二元函数取极值的条件**
> > **必要条件** 若函数 $f(x, y)$ 在点 $(x_0, y_0)$ 处取得极值，且在该点可微分，则有：  
> $$
> \frac{\partial f}{\partial x}(x_0, y_0) = 0, \quad \frac{\partial f}{\partial y}(x_0, y_0) = 0.
> $$
> 即：$(x_0, y_0)$ 是 $f(x, y)$ 的一个**驻点**（又称为临界点）。  
> **充要条件** 若 $f(x, y)$ 在点 $(x_0, y_0)$ 处具有二阶连续偏导数，且  
> $$
> \frac{\partial f}{\partial x}(x_0, y_0) = 0,\quad \frac{\partial f}{\partial y}(x_0, y_0) = 0,
> $$
> 并记二阶导数构成的判别式为  
> $$
> D = f_{xx}(x_0, y_0)f_{yy}(x_0, y_0) - [f_{xy}(x_0, y_0)]^2,
> $$
> 则：  
> > - 若 $D > 0$ 且 $f_{xx}(x_0, y_0) > 0$，则 $f(x, y)$ 在 $(x_0, y_0)$ 处取极小值；  
> >- 若 $D > 0$ 且 $f_{xx}(x_0, y_0) < 0$，则 $f(x, y)$ 在 $(x_0, y_0)$ 处取极大值；  
> >- 若 $D < 0$，则 $(x_0, y_0)$ 为**鞍点**；  
> >- 若 $D = 0$，判别方法失效，需另行分析。

### 条件极值 拉格朗日乘数法
> ==**条件极值**== 是指函数 $f(x, y, \dots)$ 在满足约束条件 $g(x, y, \dots) = 0$ 的前提下取得的极大值或极小值。此时求极值的方法不能单纯使用无约束极值的判别法。  

> ==**拉格朗日乘数法**== 是用于求**带有约束条件的极值问题**的一种重要方法。  
> 假设要求函数 $f(x, y)$ 在约束条件 $g(x, y) = 0$ 下的极值，步骤如下：
> **方法**  
> 1. 构造拉格朗日函数  
> $$
> L(x, y, \lambda) = f(x, y) + \lambda g(x, y)
> $$
> 2. 求偏导并列方程组  
> $$
> \frac{\partial L}{\partial x} = 0,\quad \frac{\partial L}{\partial y} = 0,\quad \frac{\partial L}{\partial \lambda} = 0
> $$
> 3. 解这个方程组，得到可疑点；
> 4. 将这些点代入 $f(x, y)$，比较函数值，判断极值。

> **推广**  
> 若 $f(x, y, z)$ 在约束条件  
> $$
> \begin{cases}
> g_1(x, y, z) = 0 \\
> g_2(x, y, z) = 0
> \end{cases}
> $$
> 下求极值，可构造  
> $$
> L(x, y, z, \lambda_1, \lambda_2) = f(x, y, z) + \lambda_1 g_1(x, y, z) + \lambda_2 g_2(x, y, z)
> $$
> 然后对 $x, y, z, \lambda_1, \lambda_2$ 求偏导并联立方程求解。

>  **例** 求函数 \( u = xyz \) 在附加条件 \(\frac{1}{x} + \frac{1}{y} + \frac{1}{z} = \frac{1}{a} \)（\(x,y,z,a > 0\)）下的极值。
> >**解**  
> 构造拉格朗日函数：
> $$ L(x,y,z) = xyz + \lambda \left( \frac{1}{x} + \frac{1}{y} + \frac{1}{z} - \frac{1}{a} \right) $$
> 求偏导并令其为零：
> $$
> \begin{cases}
> L_x = yz - \frac{\lambda}{x^2} = 0 \\
> L_y = xz - \frac{\lambda}{y^2} = 0 \\
> L_z = xy - \frac{\lambda}{z^2} = 0
> \end{cases}
> $$
> 将各方程乘以对应变量后相加，代入原条件得：
> $$ xyz = \frac{\lambda}{3a} $$
> 回代解得唯一驻点：
> $$ x = y = z = 3a $$
> **结论**  
> 函数在点 \((3a,3a,3a)\) 处取得极小值：
> $$ u_{\text{极小}} = 27a^3 $$

>[例子2待补充，没太看懂写了啥]

> **注**：此方程组表示函数 $L(x,y,z)$ 在三个变量方向上的变化率均为恒定值 $\theta$。
[回到主页面](index.html)

[def]: media/img/Total_differential.png