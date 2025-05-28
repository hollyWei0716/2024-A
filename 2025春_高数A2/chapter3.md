---
title: 高等数学讲义(下)
author: 胡煜成
description: 首都师范大学2025春季学期高等数学A
"og:description": 浏览器版和手机版
"og:image": https://vlook-doc.pages.dev/pic/vlook-og.png
keywords:
- 高等数学,微积分,讲义
vlook-chp-autonum: h1{{第 ### 节 }},h3{{### }}
vlook-query: vdl=on
vlook-query: ws=off
---


[回到主页面](index.html)

# 重积分

### 二重积分的概念

> [!tip]
> - **单变量积分**
> 图
> $$
S_N=\sum_{i=1}^N \Delta x \cdot f(x_i)
> $$
> $$
S=\lim_{N \to \infty} S_N=\lim_{\Delta x\to \infty}S_N
> $$
> $$
S=\int_{a}^{b} f(x) \mathrm{d}x
> $$
> - **多变量积分**
> 图
> $$
V_N=\sum_{i=1}^N \Delta A \cdot f(x_i,y_i)
>$$
> $$
V=\lim_{N \to \infty}V_N=\lim_{\Delta A\to \infty}V_N
>$$
> 二重积分公式为：
> $$
V=\iint_{D} f(x,y) \mathrm{d}A
>$$
> 其中，$D$为积分区域，$f(x,y)$为被积函数，$x,y$为积分变量，$\mathrm{d}A$为面积元
>
> **如何计算？**
> 图
> $$
M=\sum_{i=1}^N \rho (x_i,y_i)\mathrm{d}A_i=\iint_D \rho(x,y)\mathrm{d}A
>$$

###  二重积分的计算
> [!tip]
> **例1**
> > 已知$f(x,y)=1-x^2-y^2,D=\{(x,y)|0\leq x\leq 1,0\leq y\leq 1\}$,计算
> $$
\iint_D f(x,y) \mathrm{d}A
>$$
> > **解**
> > $$
\begin{aligned}
\iint_D f(x,y) \mathrm{d}A &=\iint_Df(x,y)\mathrm{d}x\mathrm{d}y\\
&=\int_0^1\int_0^1(1-x^2-y^2)\mathrm{d}x\mathrm{d}y\\
&=\int_0^1[\int_0^1(1-x^2-y^2)\mathrm{d}x]\mathrm{d}y
\end{aligned}
> > $$
> > Inner:
> > $$
\int_0^1(1-x^2-y^2)\mathrm{d}x=[x-\frac{1}{3}x^3-y^2x]_0^1=\frac{2}{3}-y^2
> >$$
> > Outer:
> > $$
\int_0^1(\frac{2}{3}-y^2)\mathrm{d}y=[\frac{2}{3}y-\frac{1}{3}y^3]_0^1=\frac{1}{3}
> > $$
> > 同理
> > $$
\begin{aligned}
\int_0^1[\int_0^1(1-x^2-y^2)\mathrm{d}x]\mathrm{d}y &= \int_0^1[\int_0^1(1-x^2-y^2)\mathrm{d}y]\mathrm{d}x \\
&=\int_0^1([y-\frac{1}{3}y^3-x^2y]_0^1)\mathrm{d}x\\
&= \int_0^1(\frac{2}{3}-x^2)\mathrm{d}x \\
&= [\frac{2}{3}x-\frac{1}{3}x^3]_0^1 \\
&=\frac{1}{3}
\end{aligned}
> > $$
>
> **例2**
> 图
> 已知$f(x,y)=1-x^2-y^2,D=\{(x,y)|x^2+y^2\leq 1,x> 0,y > 0 \} $,计算
> $$
\iint_D f(x,y) \mathrm{d}A
>$$
> > **解**
> > $$
\iint_D f(x,y) \mathrm{d}A=\int_0^1[\int_0^{\sqrt{1-x^2}}(1-x^2-y^2)\mathrm{d}y]\mathrm{d}x
> > $$
> > Inner:
> > $$
\begin{aligned}
\int_0^{\sqrt{1-x^2}}(1-x^2-y^2)\mathrm{d}y&=[y-x^2y-\frac{1}{3}y^3]_0^{\sqrt{1-x^2}} \\
&= \sqrt{1-x^2}-x^2\sqrt{1-x^2}-\frac{1}{3}(1-x^2)^{\frac{3}{2}} \\
&=\sqrt{1-x^2}(1-x^2-\frac{1}{3}(1-x^2)) \\
&= \sqrt{1-x^2}(\frac{2}{3}-\frac{2}{3}x^2)\\
&= \frac{2}{3}(1-x^2)^{\frac{3}{2}}
\end{aligned}
> > $$
> > Outer:$\int_0^1\frac{2}{3}(1-x^2)^{\frac{3}{2}}\mathrm{d}x$
> > 令$x=sin\theta,\mathrm{d}x=cos\theta\mathrm{d}\theta$
> > $$
\begin{aligned}
\int_0^1\frac{2}{3}(1-x^2)^{\frac{3}{2}}\mathrm{d}x &= \int_0^{\frac{\pi}{2}}\frac{2}{3}cos^4\theta\mathrm{d}\theta \\
&=\frac{3}{2}\int_0^{\frac{\pi}{2}}(\frac{1+cos2\theta}{2})^2\mathrm{d}\theta \\
&=\frac{3}{2}\int_0^{\frac{\pi}{2}}(\frac{1}{4}+\frac{1}{2}cos2\theta + \frac{1}{4}cos^22\theta)\mathrm{d}\theta \\
&= \frac{3}{2}([\frac{\theta}{4}]_0^{\frac{\pi}{2}}+[\frac{sin2\theta}{4}]_0^{\frac{\pi}{2}}+\frac{1}{4}\int_0^{\frac{\pi}{2}}(\frac{1+cos4\theta}{2})^2\mathrm{d}\theta )\\
&= \frac{3}{2}(\frac{\pi}{8}+\frac{\pi}{16}+\frac{1}{8}\cdot \frac{1}{4}[sin4\theta]_0^{\frac{\pi}{2}}) \\
&= \frac{\pi}{8}
\end{aligned}
> > $$

> [!tip]
> - **重积分可交换顺序？**
> 一般可以，注意上下限
> > **例1**
> > 计算 
> >$$
 \iint_{D} xy \mathrm{d}x\mathrm{d}y 
> > $$
> >其中积分区域 $ D $ 由直线 $ y = 1 $、$ x = 2 $ 及 $ y = x $ 围成。
> > >**解法一**
> > > 图
> > >$$
\begin{aligned}
\iint_{D} xy \mathrm{d}x\mathrm{d}y &= \int_{1}^{2} \left[ \int_{1}^{x} xy \mathrm{d}y \right]\mathrm{d}x \\
&= \int_1^2([\frac{1}{2}xy^2]_1^x)\mathrm{d}x \\
&= \int_1^2(\frac{x^3}{2} - \frac{x}{2})\mathrm{d}x \\
&= \left[ \frac{x^4}{8} - \frac{x^2}{4} \right]_{1}^{2}\\
&= 1+\frac{1}{8}\\
&= \frac{9}{8}
\end{aligned}
> > >$$
> > >**解法二**
> > >  图
> > >$$
\begin{aligned}
\iint_{D} xy \mathrm{d}x\mathrm{d}y &= \int_{1}^{2} \left[ \int_{y}^{2} xy \mathrm{d}x \right] \mathrm{d}y\\
&=\int_{1}^{2}([\frac{1}{2}x^2y]_y^2)\mathrm{d}y\\
&= \int_{1}^{2}(2y - \frac{y^3}{2}）\mathrm{d}y\\
&=\left[ y^2 - \frac{y^4}{8} \right]_{1}^{2}\\
&= 2-(1-\frac{1}{8})\\
&=\frac{9}{8}
\end{aligned}
> > >$$  
> >
> > **例2**
> > 计算 
> >$$ 
\iint_{D} y\sqrt{1+x^2 - y^2} \mathrm{d}\sigma
> >$$
> > 其中$ D $ 由直线 $ y = x $、$ x = -1 $ 及 $ y = 1 $ 围成的闭区域
> > > **解法一**
> > > 图
> > > $$
\begin{aligned}
\iint_{D} y\sqrt{1+x^2 - y^2} \mathrm{d}x\mathrm{d}y &= \int_{-1}^1\mathrm{d}x\int_x^1 y\sqrt{1+x^2 - y^2} \mathrm{d}y \\
&= \int_{-1}^1 [[-\frac{1}{3}(1+x^2-y^2)^{\frac{3}{2}}]_x^1] \mathrm{d}x\\
&=\int_{-1}^1\frac{1}{3}(1-|x|^3)\mathrm{d}x \\
&= \frac{2}{3}\int_0^1(1-x^3)\mathrm{d}x \\
&= \frac{1}{2}
\end{aligned}
> > > $$
> > > **解法二**
> > > 图
> > > $$
\iint_{D} y\sqrt{1+x^2 - y^2} \mathrm{d}\sigma=\int_{-1}^1 y[\int_{-1}^y\sqrt{1+x^2 - y^2} \mathrm{d}x]\mathrm{d}y
> > > $$

> [!tip]
> **极坐标下的积分**
> 已知$f(x,y)=1-x^2-y^2,D= \{(x,y)|x^2+y^2\leq 1,x\geq 0,y\geq 0 \} $,计算
> $$
\iint_D f(x,y) \mathrm{d}A
>$$
> 图
> > **解**
> > 图
> > 由于
> > $$
\mathrm{d}A=\mathrm{d}x\mathrm{d}y=r\mathrm{d}\theta\mathrm{d}r
> > $$
> > $$
\begin{aligned}
\iint_D (1-x^2-y^2)\mathrm{d}x\mathrm{d}y &=\iint_D (1-x^2-y^2)r\mathrm{d}r\mathrm{d}\theta\\
&=\iint_D(1-r^2)r\mathrm{d}r\mathrm{d}\theta\\
&= \int_0^{\frac{\pi}{2}}[\int_0^1(1-r^2)r\mathrm{d}r]\mathrm{d}\theta \\
&= \frac{\pi}{2}[\frac{1}{2}r^2-\frac{1}{4}r^4]_0^1 \\
&= \frac{\pi}{8}
\end{aligned}
> > $$

### 重积分的应用
> [!tip]
> - 质量
> - 质心(Bary center)
> 图
> $$
\iint_D\rho (x,y)\mathrm{d}x\mathrm{d}y
> $$
> $$
\bar{x}=\frac{\sum_{i=1}^nm_ix_i}{\sum_{i=1}^nm_i},\bar{y}=\frac{\sum_{i=1}^nm_iy_i}{\sum_{i=1}^nm_i}
> $$
> $$
\frac{\iint_Dx\mathrm{d}\sigma}{A}=\bar{x}=\frac{\iint_Dx\mu (x,y)\mathrm{d}\sigma}{\iint_D\mu (x,y)\mathrm{d}\sigma} \\ \frac{\iint_Dy\mathrm{d}\sigma}{A}=\bar{y}=\frac{\iint_Dy\mu (x,y)\mathrm{d}\sigma}{\iint_D\mu (x,y)\mathrm{d}\sigma}
> $$

### 复习
> [!tip]
> - 一般区域的二重积分
> - 积分变换顺序
> - 换元法：极坐标.被积函数更简单/积分区域更简单
> - 应用：质量，面积，转动惯量
> 图
> $$
I=\iint_D\mu (x,y)r^2(x,y)\mathrm{d}x\mathrm{d}y=\sum_{i=1}^Nm_ir_i^2
> $$
> 其中，$\mu (x,y)$是密度，$)\mathrm{d}x\mathrm{d}y$是面积元
> 密度*面积元=质量
>
> > **例1**
> > 图
> > > **解**
> > > $$
\begin{aligned}
I&=\iint_Dr^2(\rho,\theta)\rho \mathrm{d}\rho \mathrm{d}\theta \\ 
&= \int_{-\frac{\pi}{2}}^{\frac{\pi}{2}}\int_0^{2cos\theta}\rho^3\mathrm{d}\rho \mathrm{d}\theta \\ 
&=\int_{-\frac{\pi}{2}}^{\frac{\pi}{2}}[\frac{1}{4}\rho^4]_0^{2cos\theta}\mathrm{d}\theta \\ 
&=\int_0^{\frac{\pi}{2}}4sos^4\theta \mathrm{d}\theta \\
&=\frac{3}{2}\pi
\end{aligned}
> > > $$
> >
> > **例2**
> > 图
> > > **解**
> > >$$
\begin{aligned}
I&=\iint_Dr^2(\rho,\theta)\rho \mathrm{d}\rho \mathrm{d}\theta\\
&= \int_{-\frac{\pi}{2}}^{\frac{\pi}{2}}\int_0^{2cos\theta}(1+\rho^2-2\rho cos\theta)\rho \mathrm{d}\rho \mathrm{d}\theta \\
&=\frac{\pi}{2}
\end{aligned}
> > >$$
> > >$$
I=\int_0^{2\pi}\int_0^1\rho^2\cdot \rho\mathrm{d}\rho \mathrm{d}\theta=\frac{\pi}{2}
> > >$$
> $$
I=\iint_D\mu(x,y)r^2(x,y)\mathrm{d}x\mathrm{d}y
> $$
> $$
I(x_0,y_0)=\iint_D\mu (x,y) [(x-x_0)^2+(y-y_0)^2]\mathrm{d}x\mathrm{d}y
> $$
> $$
\frac{\partial I}{\partial x_0}=\iint_D2\mu(x,y)(x-x_0)\mathrm{d}x\mathrm{d}y=0 \\ \frac{\partial I}{\partial y_0}=\iint_D2\mu(x,y)(y-y_0)\mathrm{d}x\mathrm{d}y=0
> $$
> 从而
>$$
\iint_D\mu x_0\mathrm{d}x\mathrm{d}y=\iint_D\mu x\mathrm{d}x\mathrm{d}y
>$$
>得
>$$
x_0=\frac{\iint_D\mu x\mathrm{d}x\mathrm{d}y}{\iint_D\mu \mathrm{d}x\mathrm{d}y} \\ y_0=\frac{\iint_D\mu y\mathrm{d}x\mathrm{d}y}{\iint_D\mu \mathrm{d}x\mathrm{d}y}
>$$
>$$
\begin{cases}
x_0=\frac{\sum m_ix_i}{\sum m_i},加权平均 \\
y_0=\frac{\sum m_iy_i}{\sum m_i},加权平均 
\end{cases}
>$$
>
> **平行轴定理**
> 图
> $$
\begin{aligned}
I(x_0,y_0)&=\iint_D\mu [(x-x_0)^2+(y-y_0)^2]\mathrm{d}x\mathrm{d}y \\
&=\iint_D\mu [(x-x_c+x_c-x_0)^2+(y-y_c+y_c-y_0)^2]\mathrm{d}x\mathrm{d}y \\
&=\iint_D\mu [(x-x_c)^2+(y-y_c)^2]\mathrm{d}x\mathrm{d}y+\iint_D\mu [(x_c-x_0)^2+(y_c-y_0)^2]\mathrm{d}x\mathrm{d}y+2\iint_D\mu (x_c-x_0)(x-x_0)\mathrm{d}x\mathrm{d}y+2\iint_D\mu (y_c-y_0)(y-y_0)\mathrm{d}x\mathrm{d}y \\
&=I_c+Mr^2
\end{aligned}
> $$
> > **例3**
> > 求球体 $ x^2 + y^2 + z^2 \leq 4a^2 $ 被圆柱面 $ x^2 + y^2 = 2ax $ ($ a > 0 $) 截得的含在圆柱面内的立体体积
> > 图
> > > **解**
> > > $$
\begin{aligned}
V&= 4 \iint_{D} \sqrt{4a^2 - x^2 - y^2}\mathrm{d}x\mathrm{d}y \\
&=4\int_0^{\frac{\pi}{2}}\int_0^{2acos\theta}\sqrt{4a^2 - \rho^2 }\rho \mathrm{d}\rho \mathrm{d}\theta \\
&=4\int_0^{\frac{\pi}{2}}\frac{8}{3}a^3(1-sin^3\theta) \mathrm{d}\theta \\ 
&= \frac{16}{3}a^3\pi-\frac{8}{3}\cdot\frac{8}{3}a^3 \\
&= \frac{32}{3}a^3(\frac{\pi}{2}-\frac{2}{3})
\end{aligned}
> > > $$

> [!tip]
> **换元法**
> $$
(x,y) \to (u,v)
> $$
> > **例1**：椭圆面积
> > 图
> > 已知$\frac{x^2}{a^2}+\frac{y^2}{b^2}=1$，求
> > $$
\iint_D\mathrm{d}x\mathrm{d}y
> > $$
> > > **解**
> > > $$
\begin{aligned}
\iint_D\mathrm{d}x\mathrm{d}y &= 4\int_0^a\int_0^{b\sqrt{1-\frac{x^2}{a^2}}}\mathrm{d}y\mathrm{d}x \\
&=4\int_0^ab\sqrt{1-\frac{x^2}{a^2}}\mathrm{d}y
\end{aligned}
> > > $$
> > > 令$y=asin\theta,\mathrm{d}y=acos\theta\mathrm{d}\theta$,则
> > > $$
原式=4\int_0^{\frac{\pi}{2}}bcos\theta a cos\theta\mathrm{d}\theta=4ab\int_0^{\frac{\pi}{2}}\frac{1+cos2\theta}{2}\mathrm{d}\theta=\pi ab
> > > $$
> > > **解法二**
> > > 令$x=au,y=bv,-1\leq u \leq 1,-1\leq v \leq 1,u^2+v^2=1$，则
> > > $$
\mathrm{d}x=a\mathrm{d}u \\ \mathrm{d}y=b\mathrm{d}v \\ \mathrm{d}x\mathrm{d}y=a\mathrm{d}u  \cdot b\mathrm{d}v
> > > $$
> > > $$
\iint_D\mathrm{d}x\mathrm{d}y= \iint_Dab\mathrm{d}u\mathrm{d}v=\pi ab
> > > $$
>
> 已知
> $$
\begin{cases}
u=u(x,y)\\
v=v(x,y)
\end{cases}
> $$
> 则
> $$
\begin{cases}
\mathrm{d}u=\frac{\partial u}{\partial x}\mathrm{d}x+\frac{\partial u}{\partial y}\mathrm{d}y \\
\mathrm{d}v=\frac{\partial v}{\partial x}\mathrm{d}x+\frac{\partial v}{\partial y}\mathrm{d}y
\end{cases}
> $$
> 可以写成如下形式
> $$
\begin{bmatrix}
\mathrm{d}u\\
\mathrm{d}v
\end{bmatrix}=
\begin{bmatrix}
\frac{\partial u}{\partial x} & \frac{\partial u}{\partial y}\\
\frac{\partial v}{\partial x} & \frac{\partial v}{\partial y}
\end{bmatrix}
\begin{bmatrix}
\mathrm{d}x\\
\mathrm{d}y
\end{bmatrix}
> $$
> 图
> $$
\mathrm{d}u\mathrm{d}v = J= \frac{\partial (u,v)}{\partial (x,y)}=
\begin{vmatrix}
\frac{\partial u}{\partial x}\mathrm{d}x & \frac{\partial u}{\partial y}\mathrm{d}y\\
\frac{\partial v}{\partial x}\mathrm{d}x & \frac{\partial v}{\partial y}\mathrm{d}y
\end{vmatrix}=|\frac{\partial u}{\partial x}\frac{\partial v}{\partial y}-\frac{\partial u}{\partial y}\frac{\partial v}{\partial x}|\mathrm{d}x\mathrm{d}y
> $$
>
> > **例2**
> > 已知
> > $$
\begin{cases}
u=3x-2y\\
v=x+y
\end{cases}
> > $$
> > 图
> > > **解**
> > > 方法一：
> > > $$
|\vec{w_1}\times\vec{w_2}|=|\vec{w_1}|\cdot |\vec{w_2}|\cdot sin\theta=
\begin{vmatrix}
3 & -2\\
1 & 1
\end{vmatrix}=5
> > > $$
> > > 方法二：
> > > $$
J=
\begin{vmatrix}
\frac{\partial u}{\partial x} & \frac{\partial u}{\partial y}\\
\frac{\partial v}{\partial x} & \frac{\partial v}{\partial y}
\end{vmatrix}=
\begin{vmatrix}
3 & -2\\
1 & 1
\end{vmatrix}=5
> > > $$
> > > 则
> > > $$
\mathrm{d}u\mathrm{d}v=\frac{\partial (u,v)}{\partial (x,y)}\mathrm{d}x\mathrm{d}y=5\mathrm{d}x\mathrm{d}y
> > > $$
> > > $$
\iint_D\mathrm{d}x\mathrm{d}y=\iint_D\frac{1}{5}\mathrm{d}u\mathrm{d}v
> > > $$
>
> $$
\mathrm{d}u\mathrm{d}v=|J|\mathrm{d}x\mathrm{d}y=|\frac{\partial (u,v)}{\partial (x,y)}|\mathrm{d}x\mathrm{d}y
> $$
> 则
> $$
\mathrm{d}x\mathrm{d}y=|\frac{\partial (x,y)}{\partial (u,v)}|\mathrm{d}u\mathrm{d}v
> $$
> 若
> $$
\begin{cases}
x=\rho cos\theta\\
y=\rho sin\theta
\end{cases}
> $$
> 则
> $$
J(\rho ,\theta)=\frac{\partial (x,y)}{\partial (\rho ,\theta)}=
\begin{vmatrix}
\frac{\partial x}{\partial \rho } & \frac{\partial x}{\partial \theta}\\
\frac{\partial y}{\partial \rho } & \frac{\partial y}{\partial \theta}
\end{vmatrix}=
\begin{vmatrix}
cos\theta & -\rho sin\theta\\
sin\theta & \rho cos\theta
\end{vmatrix} = \rho
> $$
> $$
\mathrm{d}x\mathrm{d}y=|\rho|\mathrm{d}\rho\mathrm{d}\theta=\rho\mathrm{d}\rho\mathrm{d}\theta
> $$
> $$
|\frac{\partial (x,y)}{\partial (u,v)}|=|\frac{\partial (u,v)}{\partial (x,y)}|^{-1}
> $$
> 以例2为例
> $$
|\frac{\partial (u,v)}{\partial (x,y)}|=5 \\ 
\mathrm{d}x\mathrm{d}y=|\frac{\partial (x,y)}{\partial (u,v)}|=\frac{1}{5}\mathrm{d}u\mathrm{d}v
> $$
> $$
\begin{bmatrix}
\frac{\partial x}{\partial u} & \frac{\partial x}{\partial v}\\
\frac{\partial y}{\partial u} & \frac{\partial y}{\partial v}
\end{bmatrix}
与
\begin{bmatrix}
\frac{\partial u}{\partial x} & \frac{\partial u}{\partial y}\\
\frac{\partial v}{\partial x} & \frac{\partial v}{\partial y}
\end{bmatrix}互逆
> $$
>
> > **例**
> >计算
> >$$
\int_{-\infty}^{+\infty}e^{-x^2}\mathrm{d}x
> >$$
> > > **解**
> > > 令$I=\int_{-\infty}^{+\infty}e^{-x^2}\mathrm{d}x$
> > > 则
> > > $$
I^2=\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty}e^{-(x^2+y^2)}\mathrm{d}x\mathrm{d}y=\int_{-\infty}^{+\infty}e^{-y^2}\mathrm{d}y\int_{-\infty}^{+\infty}e^{-x^2}\mathrm{d}x
> > > $$
> > > 令$x=rcos\theta,y=rsin\theta$，则
> > > $$
\begin{aligned}
I^2 &=\int_0^{2\pi}\int_0^{+\infty}e^{-r^2}r\mathrm{d}r\mathrm{d}\theta \\ 
&=\int_0^{2\pi}\mathrm{d}\theta(\frac{1}{2}\int_0^{+\infty}e^{-r^2}\mathrm{d}r^2 )\\
&=\frac{1}{2}\int_0^{2\pi}[(-e^{-r^2})]_0^{+\infty}\mathrm{d}\theta \\
&= \pi
\end{aligned}
> > > $$
> > > 故
> > > $$
\int_{-\infty}^{+\infty}e^{-x^2}\mathrm{d}x = I=\sqrt{\pi}
> > > $$

### 三重积分
> [!tip]
> $$
\iiint_{\Omega}f(x,y,z)\mathrm{d}x\mathrm{d}y\mathrm{d}z
> $$
> 其中，$f(x,y,z)$是密度，所求为质量
> > **例1**
> > 计算
> > $$
\iiint_{\Omega}x\mathrm{d}x\mathrm{d}y\mathrm{d}z
> > $$
> > 其中积分区域 $\Omega$ 由平面 $x + 2y + z = 1$ 与三个坐标平面 ($x=0$, $y=0$, $z=0$) 围成
> > 图
> > > **解法一**
> > > $$
\begin{aligned}
\iiint_{\Omega}x\mathrm{d}x\mathrm{d}y\mathrm{d}z 
&=\int_0^1\mathrm{d}z\int_0^{\frac{1}{2}(1-z)}\mathrm{d}y\int_0^{1-2y-z}x\mathrm{d}x \\
&=\int_0^1\mathrm{d}z\int_0^{\frac{1}{2}(1-z)}\frac{1}{2}(1-2y-z)^2\mathrm{d}y \\
&= \frac{1}{2} \int_{0}^{1} \left[ -\frac{(1 - 2y - z)^3}{6} \right]_{0}^{\frac{1}{2}(1 - z)} \mathrm{d}z \\
&= \frac{1}{12} \int_{0}^{1} (1 - z)^3 \, \mathrm{d}z \\
&= \frac{1}{12} \left[ -\frac{(1 - z)^4}{4} \right]_{0}^{1} \\
&= \frac{1}{48}.
\end{aligned}
> > > $$
> > > **解法二**
> > > $$
\begin{aligned}
\iiint_{\Omega}x\mathrm{d}x\mathrm{d}y\mathrm{d}z
&=\int_0^1\mathrm{d}x\int_0^{\frac{1}{2}(1-x)}\mathrm{d}y\int_0^{1-x-2y} x \mathrm{d}z \\
&=\int_0^1x\mathrm{d}x\int_0^{\frac{1}{2}(1-x)}(1-x-2y)\mathrm{d}y \\ 
&=\int_0^1\frac{1}{4}x(1-x)^2\mathrm{d}x \\
&= \frac{1}{48}
\end{aligned} 
> > > $$
> >
> > **例2**
> > 利用柱面坐标计算三重积分 
> > $$
\iiint_{\Omega} z \mathrm{d}x\mathrm{d}y\mathrm{d}z
> > $$
> > 其中积分区域 $\Omega$ 由曲面 $z = x^2 + y^2$ 与平面 $z = 4$ 围成的闭区域
> > 图
> > > **解**
> > > 令
> > > $$
\begin{cases}
x=\rho cos\theta \\
y=\rho sin\theta \\
z=z
\end{cases}
> > > $$
> > > 则
> > > $$
\mathrm{d}V=\mathrm{d}x\mathrm{d}y\mathrm{d}z=\rho\mathrm{d}\rho\mathrm{d}\theta\mathrm{d}z
> > > $$
> > > $$
\begin{aligned}
\iiint_{\Omega} z \mathrm{d}x\mathrm{d}y\mathrm{d}z
&=\iiint_{\Omega} z \rho\mathrm{d}\rho\mathrm{d}\theta\mathrm{d}z \\ 
&=\int_0^4\mathrm{d}z\int_0^{2\pi}\mathrm{d}\theta\int_0^{\sqrt{z}} z \rho \mathrm{d}\rho \\
&=\int_0^4\mathrm{d}z\int_0^{2\pi}\frac{1}{2}z^2\mathrm{d}\theta \\
&=\int_0^4 z^2\pi \mathrm{d}z \\
&=\frac{1}{3}\pi [z^3]_0^4 \\
&=\frac{64}{3}\pi
\end{aligned}
> > > $$




[回到主页面](index.html)