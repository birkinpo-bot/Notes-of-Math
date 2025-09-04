# Obstruction Theory

在代数拓扑中我们关心给定 CW 复形 $K$, $Y$ 之间的映射同伦类 $[K,Y]$, 我们的想法是利用 CW 复形结构, 从 $0$ 维胞腔 $K^{(0)}$ 逐步延拓连续映射以及同伦, 在构造过程中我们有可能碰到障碍, 我们会发现这个障碍可以用一个特别的上同调元表征, 这就是障碍理论的大致内容.

我们假定空间 $Y$ 是道路连通 ($\pi_0(Y)$ 平凡) 的且 $\rm{abelian}$, 即对 $\forall\, q\geq1$, $\pi_1(Y)$ 在 $\pi_q(Y)$ 上的作用平凡. 这意味我们可以无歧义地使用记号 $\pi_q=\pi_q(Y)$,  特别地, 这意味着 $\pi_1(Y)$ 是 $\text{Abel}$ 群, 从而能成为同调的系数群. 

### Obstruction cochain

假设 $K$ 有一个 CW 复形结构 $K=\cup_{q}K^{(q)}$, 我们可以从 $0$-胞腔 $K^{(0)}$ 开始逐步构造到 $Y$ 的连续映射. 首先 $K^{(0)}$ 就是一些离散点, 因此很容易构造 $f:K^{(0)}\to Y$. 因为 $Y$ 是道路连通的, 因此可以通过连接不同点之间的道路将 $f$ 延拓至 $K^{(1)}$. 

**定义**: 若我们已经有 $f:K^{(q)}\to Y$, 为了将 $f$ 延拓至 $K^{(q+1)}$, 我们需要分析每个 $(q+1)$-胞腔 $\sigma$. 假设 $\phi_{\sigma}:S^{q}\to K^{(q)}$ 是 $\sigma$ 对应的粘合映射, 则有映射 $f\circ\phi_{\sigma}:S^q\to Y$. 于是每一个 $\sigma$ 都将对应 $\pi_q(Y)$ 中的一个元素 $[f\circ\phi_{\sigma}]$, <span style="color:yellow">且 $f$ 能延拓至 $K^q\cup_{\phi_{\sigma}}D^{q+1}$ 当且仅当 $[f\circ\phi_\sigma]$ 是平凡的.</span> 我们由此得到一个上链 $c(f)\in C^{q+1}(K;\pi_q)$: 
$$
\begin{align*}
c(f):C_{q+1}^{cell}(K)&\to\pi_q(Y) \\
\sigma&\mapsto[f\circ\phi_\sigma]
\end{align*}
$$
称 $c(f)$ 为 $f$ 的**障碍上链(obstruction cochain)**. 根据定义, $f$ 可延拓至 $K^{(q+1)}$ 当且仅当 $c(f)=0$.  

**性质**: 关于障碍链 $c(f)$ 我们有如下两个基本性质: 

1. $c(f)$ 具有自然性, 也即若 $k:K'\to K$ 是 CW 复形之间的映射, $f:K^{(q)}\to Y$, 则
   $$
   c(f\circ k)=h^*c(f)
   $$
   其中 $f\circ k:K'^{(q)}\to Y$, $k^*$ 为 $k$ 诱导的上链复形 $C^{q+1}(K;\pi_q)$ 到 $C^{q+1}(K';\pi_q)$ 的同态. 

2. 若 $f_0, f_1:K^q\to Y$ 同伦, 也即存在 $h:K^q\times I\to Y$ 连接 $f_0$ 和 $f_1$, 则 $c(f_0)=c(f_1)$. 这是因为对每一个 $(q+1)$-胞腔 $\sigma$ 都有 $f_0\circ\phi_\sigma \simeq f_1\circ\phi_\sigma$. 

3. 结合两者能得到 $c(f)$ 的同伦不变性. 特别地, 这说明 $c(f)$ 与 $K$ 的 CW 复形结构选取无关. 

**定理**: $\delta c(f)=0$, 即 $c(f)$  是一个上闭链, 因此定义了一个上同调元素. 

证明: $\text{Step 1:}$ 首先假设 $K^{q}$ 是 $q$-连通的, 则由 $\mathrm{Hurewicz}$ 定理 
$$
\pi_q(K^q)\cong H_q(K^q)=Z_q(K^q)=Z_q(K)
$$
其中第二个等号是因为 $K^q$ 没有大于 $q$ 维的胞腔, 记该同构为 $\psi:Z_q(K)\to\pi_q(K^q)$. 则 $f$ 可分解为如下映射的复合
$$
C_{q+1}(K)\xrightarrow{\partial}Z_q(K)\xrightarrow{\psi}\pi_q(K^q)\xrightarrow{f_*}\pi_q(Y)
$$
读者可从 $f$ 的定义看出其正确性. 因为 $Z_q(K) = \ker\partial\subset C_q(K)$ 是直和项, 所以 $f_*\circ\psi$ 可延拓成为 $\eta:C_q(K)\to \pi_q$. 于是对 $\forall\,\sigma\in C_{q+1}(K)$, 
$$
c(f)(\sigma) = \eta(\partial\sigma) = (\delta\eta)(\sigma)
$$
也即 $c(f) = \delta\eta$, 自然是上闭链.

$\mathrm{Step 2:}$ 一般情况下, 对任一 $(q+1)$-胞腔 $\zeta$, 设 $K'\subset K$ 为 $\zeta$ 及其边界组成的子复形, $f' = f\big|_{K'^{(q)}}$, 则 $c(f') = c(f)\big|_{K'}$ 且因为 $K'^{(q)}$ 是 $q$-连通的, $c(f')$ 是上边缘链,  所以
$$
\delta c(f)(\zeta) = \delta c(f')(\zeta) = 0
$$


### Difference cochain

**定义**: 假设有映射 $f_0,f_1:K^{(q)}\to Y$ 且 $f_0|_{K^{(q-1)}}\simeq f_1|_{K^{(q-1)}}$, 同伦映射为 $h:K^{(q-1)}\times I\to Y$. 空间 $K\times I$ 有一个乘积 CW 复形结构, 其 $q$-骨架为
$$
(K\times I)^{(q)} = (K^{(q)}\times \{0,1\})\cup(K^{(q-1)}\times I)
$$
我们利用 $f_0,f_1$ 和 $h$ 构造 $F:(K\times I)^{(q)}\to Y$: 
$$
\begin{equation*}
F(x,t) = 
\begin{cases}
f_i(x),&(x,t)\in K^{(q)}\times\{i\},\;i=0,1 \\
h(x,t),&(x,t)\in K^{(q-1)}\times I.
\end{cases}
\end{equation*}
$$
$F$ 延拓至 $(K\times I)^{(q+1)}$ 的障碍被上闭链 $c(F)\in C^{q+1}(K\times I;\pi_q)$ 刻画, 注意到 
$$
\begin{align*}
C_{q}(K)&\to C_{q+1}(K\times I) \\
\sigma&\mapsto\sigma\times I
\end{align*}
$$
给出一个群同构, 因此 $c(F)$ 可看作 $C^q(K;\pi_q)$ 中的元素, 它将 $\sigma\in C_q(K)$ 对应到 $c(F)(\sigma\times I)$. 由此我们定义一个上链
$$
d(f_0,h,f_1)\in C^q(K;\pi_q),\quad d(f_0,h,f_1)(\sigma):=(-1)^{q+1}c(F)(\sigma\times I),\; \forall\,\sigma\in C_q(K).
$$
称其为**形变上链(deformation cochain)**. 特别地, 当 $f_0\big|_{K^{(q-1)}}=f_1\big|_{K^{(q-1)}}$ 且 $h$ 为平凡同伦时, 我们记得到的上链为 $d(f_0,f_1)$, 并称其为**差异上链(difference cochain)**. 

根据定义, $d(f_0,h,f_1) = 0$ 当且仅当 $h$ 可延拓为 $f_0\big|_{K^{(q)}}\simeq f_1\big|_{K^{(q)}}$; 

类似地, $d(f_0,f_1) = 0$ 当且仅当 $f_0\big|_{K^{(q-1)}} = f_1\big|_{K^{(q-1)}}$ 可延拓为 $f_0\big|_{K^{(q)}}\simeq f_1\big|_{K^{(q)}}$.

**性质**: 关于形变上链我们有如下两个简单的性质:

1. 自然性: 设有 $k:K'\to K$ 以及 $f_0,f_1,h$ 如上, $f_0',f_1',h'$ 为前者分别复合 $k$​ 后得到的映射, 则
   $$
   k^*d(f_0,h,f_1) = d(f_0',h',f_1')
   $$

2. 加法公式: 设有 $f_0,f_1,f_2:K^q\to Y$ 且 $f_0\big|_{K^{(q-1)}}\overset{h}{\simeq} f_1\big|_{K^{(q-1)}},\, f_1\big|_{K^{(q-1)}}\overset{h'}{\simeq} f_2\big|_{K^{(q-1)}}$, 将 $h$ 和 $h'$ 相接能得到 $f_0\big|_{K^{(q-1)}}\overset{h''}{\simeq} f_1\big|_{K^{(q-1)}}$, 则有
   $$
   d(f_0,h'',f_2) = d(f_0,h,f_1) + d(f_1,h',f_2)
   $$

一般情况下 $d(f_0,h,f_1)$ 不是上闭链, 但存在如下有趣的公式: 

**定理**(上边缘公式): $\delta d(f_0,h,f_1) = c(f_0) - c(f_1)$. 

证明: 记 $d=d(f_0,h,f_1)$, 由定义, 对 $\forall\,\sigma\in C^{q+1}(K)$, 
$$
\begin{align*}
(\delta d)(\sigma) &= d(\partial\sigma) = (-1)^{q+1}c(F)((\partial\sigma)\times I) \\
&= (-1)^{q+1}c(F)\Big(\partial(\sigma\times I)-(-1)^{q+1}(\sigma\times\partial I)\Big) \\
&= -c(F)(\sigma\times1-\sigma\times0) \\
&= c(f_0) - c(f_1)
\end{align*}
$$
其中倒数第二个等式的原因是 $c(F)$ 为上闭链. 

**推论**: 特别地, 若 $f_0,f_1$ 都是定义在 $K$ 上的映射, 则 $c(f_0) = c(f_1) = 0$, 此时 $d(f_0,h,f_1)$ 是上闭链. 

### 映射和同伦的扩张问题

为了接下来的讨论, 我们需要一个有用的引理: 

**引理**: 设有映射 $f_0:K^{(q)}\to Y$, 对任意上链 $d\in C^{q}(K;\pi_q)$, 都存在映射 $f_1:K^{(q)}\to Y$ 使得 $f_0\big|_{K^{(q-1)}} = f_1\big|_{K^{(q-1)}}$ 且 $d(f_0,f_1) = d$. 

证明: 稍后



**定理**: 设有映射 $f:K^{(q-1)}\to Y$, 若 $f$ 能延拓为 $f':K^{(q)}\to Y$, 则障碍上链 $c(f')$ 所决定的上同调类 $[c(f')]\in H^{q+1}(K;\pi_q)$ 不依赖延拓 $f'$ 的选取, 且 $f$ 能延拓至 $K^{(q+1)}$ 当且仅当 $[c(f')] = 0$. 

**注**: 我们一般用 $\bar{c}(f)$ 表示该上同调类. 

证明: $\mathrm{(i)}$ 设 $f_0,f_1$ 是两个不同的延拓, 则由上边缘公式 $c(f_0) - c(f_1) = \delta d(f_0,f_1)$, 所以 $[c(f_0)]=[c(f_1)]$. 

$\mathrm{(ii)}$ 若 $f$ 能延拓为 $f'':K^{(q+1)}\to Y$, 则由障碍上链的定义, $c(f''\big|_{K^{(q)}}) = 0$, 自然 $\bar{c}(f) = 0$. 

$\mathrm{(iii)}$ 若 $[c(f')] = 0$, 则存在 $d\in C^{q}(K;\pi_q)$ 使得 $c(f') = \delta d$. 由引理, 存在 $f_1':K^{(q)}\to Y$ 使得 $f_1'\big|_{K^{(q-1)}} = f'\big|_{K^{(q-1)}} = f$ 且 $d(f',f_1') = d$, 由上边缘公式 $c(f_1') = c(f') - \delta d = 0$. 这说明 $f_1'$ 可延拓至 $K^{(q+1)}$. 



对于形变上链我们也有类似的定理, 这个定理讨论的是两个整体定义的映射之间的同伦能否延拓的问题.

**定理**: 设 $f_0,f_1:K\to Y$, 且 
$f_0\big|_{K^{(q-2)}}\overset{h}{\simeq}f_0\big|_{K^{(q-2)}}$. 
若 $h$ 能延拓为 
$f_0\big|_{K^{(q-1)}}\overset{h'}{\simeq} f_0\big|_{K^{(q-1)}}$. 
则上同调类 $[d(f_0,h,f_1)]\in H^q(K;\pi_q)$ 与延拓 $h'$ 无关 (注意由**推论**知形变上链是闭的, 因此能定义一个上同调类), 且 $h$ 能延拓为 $f_0\big|_{K^{(q)}}\overset{h''}{\simeq} f_1\big|_{K^{(q)}}$ 当且仅当 $[d(f_0,h,f_1)] = 0$. 

**注**: 我们一般用 $\bar{d}(f_0,h,f_1)$ 表示该上同调类. 

因为 CW 复形对总是满足同伦延拓性, 我们能得到: 

**定理**: 设 $f_0,f_1:K\to Y$, 且 $f_0\big|_{K^{(q-1)}} = f_1\big|_{K^{(q-1)}}$ (于是能定义 $d(f_0,f_1)$). 则存在 $f_1':K\to Y$ 使得 
$f_1'\big|_{K^{(q)}} = f_1\big|_{K^{(q)}}$ 且 
$f_1'\simeq f_0\; (\mathrm{rel.}\;K^{(q-2)})$ 
当且仅当 $\bar{d}(f_0,f_1) = 0$. 

### 映射同伦类 $[K,Y]$ 的分类问题

在这一节我们要求目标空间 $Y$ 是 $(q-1)$-连通的, 在这一假设下, 我们有: 

**性质**: 若 CW 复形 $K$ 的维数不超过 $(q-1)$, 则 $K$ 到 $(q-1)$-连通空间 $Y$ 的任意两个映射 $f_0,f_1$ 都是同伦等价的; 或者等价地说, 任意从 $K$ 到 $Y$ 的映射都是零伦的. 

证明: 因为 $Y$ 是道路连通空间, 我们很容易构造 $f_0\big|_{K^{(0)}}$ 与 $f_1\big|_{K^{(0)}}$ 之间的同伦 $h$, 因为 $\pi_1=\cdots=\pi_{q-1}=0$, 所以 $h$ 延拓至整个 $K$ 的障碍全都消失, 因此 $f_0\overset{h}{\simeq}f_1$. 特别地, $f_0\simeq\text{const}$. 

**定理**: 对于任意 $q$ 维 CW 复形 $(K,*)$ 以及 $(q-1)$-连通空间 $(Y,y_0)$, 存在如下一一对应关系
$$
[K,Y]\longleftrightarrow H^q(K;\pi_q)
$$