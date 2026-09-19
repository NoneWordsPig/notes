# 第1章 数列的极限

极限理论是微积分学的重要基础, 用极限的思想和方法来处理和解决变量问题是微积分中的基本方法. 特别是极限中 “无穷” 的概念, 在学习极限理论中起着关键的作用. 本章主要介绍数列极限的概念、理论和运算方法, 这是学习微积分的第一步.

## §1.1 数列

### 一、数列及其极限的概念

极限过程是微积分的核心思想, 它的主要特征之一是与无穷的概念密切相关, 而数列是分析极限过程的主要工具. 所谓数列, 顾名思义是指一个接着一个并且永无止境的数的排列. 例如

$$
\begin{array}{c} 1, 2, 3, 4, \dots , n, \dots \\ 1, q, q ^ {2}, q ^ {3}, \dots , q ^ {n - 1}, \dots , \\ 1, - 1, 1, - 1, \dots , (- 1) ^ {n - 1}, \dots , \\ 1, 0, 2, 0, 3, 0, \dots , \frac {1 + (- 1) ^ {n - 1}}{2} \cdot \frac {n + 1}{2}, \dots \end{array}
$$

都是数列, 以下我们给出数列的一般定义.

**定义 1.1.1** 定义域是正整数集  $N_{+}$  的一个函数  $f: N_{+} \rightarrow R$  称为一个数列, 记为  $a_{1}, a_{2}, \cdots, a_{n}, \cdots$  或者  $\{a_{n}\}$ , 其中  $a_{n} = f(n)$  称为通项. 若 f 是有界函数, 则称  $\{a_{n}\}$  是有界数列; 否则称  $\{a_{n}\}$  是无界数列.

给出一个数列最常见的方法是给出决定通项的法则或公式, 如

$$
1, \frac {1}{2}, \frac {1}{3}, \frac {1}{4}, \dots , \frac {1}{n}, \dots
$$

是由通项 $a_{n} = \frac{1}{n}$ 决定的数列.

给出数列的另一种方法是用递推公式表示, 如著名的斐波那契 $^{①}$ 数列:  $a_{1} = a_{2} = 1$ ,  $a_{n+1} = a_{n} + a_{n-1}, n \geqslant 2$ . 它的前几项是1, 1, 2, 3, 5, 8, 13, 21, 34.

对数列 $\{a_{n}\}$ ，若

$$
a _ {n} \leqslant a _ {n + 1} (\text {或} a _ {n} \geqslant a _ {n + 1}), \quad n = 1, 2, 3, \dots ,
$$

则称 $\{a_{n}\}$ 为单调增加数列 (或单调减少数列).

单调增加数列和单调减少数列统称为单调数列.

如果上述不等号严格成立, 那么称 $\{a_{n}\}$ 为严格单调增加数列 (或严格单调减少数列).

在数列中, 所谓有极限的数列特别得到重视, 有极限的数列也称为收敛数列. 收敛数列粗略地讲是指当 $n$ 越来越大时, $a_{n}$ 会和某个数无限地接近. 例如, 数列

$$
1, \frac {1}{2}, \frac {1}{3}, \frac {1}{4}, \dots , \frac {1}{n}, \dots ,
$$

当 $n$ 越来越大时, $a_{n} = \frac{1}{n}$ 越来越接近于常数0; 数列

$$
\frac {1}{2}, \frac {2}{3}, \frac {3}{4}, \frac {4}{5}, \dots , \frac {n}{n + 1}, \dots ,
$$

当 $n$ 越来越大时, $a_{n} = \frac{n}{n + 1}$ 越来越接近于常数1, 等等.

显然, “越来越大” “越来越接近” 并不是严谨的数学语言. 对于上述严格单调减少数列 $\left\{\frac{1}{n}\right\}$ 和严格单调增加数列 $\left\{\frac{n}{n+1}\right\}$, 这样表达还容易接受, 但如果一个收敛数列不是单调数列, 那么这样表述极限就很不 “精确” 了. 下面我们给出数列收敛的准确定义.

**定义 1.1.2** 设  $\{a_{n}\}$  是 R 中的一个数列. 如果存在  $a \in R$ , 使得  $\forall \varepsilon > 0$ ,  $\exists N \in N_{+}$ , 当  $n \geqslant N$  时, 都有

**重难点讲解数列极限的定义**

$$
\left| a _ {n} - a \right| <   \varepsilon ,
$$

就称数列 $\{a_{n}\}$ 是收敛的并且收敛于 $a$ (或趋于 $a$), 记为

$$
\lim _ {n \to \infty} a _ {n} = a \quad \text {或者} \quad \text {当} n \to \infty \text {时,} a _ {n} \to a.
$$

数列的极限

这时称 $a$ 是数列 $\{a_{n}\}$ 的极限. 如果上述条件不成立, 就称 $\{a_{n}\}$ 是发散的或者不收敛.

> **注：** 1,1,2,3,5,8,13,21,…

> **注：** ① 斐波那契 (Fibonacci, 1170—1250), 意大利数学家, 斐波那契在《算盘书》中提出了一个有趣的兔子问题, 从而得到著名的斐波那契数列 1,1,2,3,5,8,13,21, $\cdots$ . 他是西方第一个研究斐波那契数列的人, 并将现代书写数和乘数的位值表示法系统引入欧洲.

第1章

根据数列极限的定义, 容易得到常数列 $\{a_{n}\}$, $a_{n} = c (c \in \mathbb{R})$ 的极限为 $c$, 即 $\lim_{n \to \infty} c = c$

需要特别指出的是, 在定义 1.1.2 中, $\varepsilon$ 是任意给定的, 即不管 $\varepsilon$ 多么小, 总可以找到正整数 $N$, 使得当 $n \geqslant N$ 时, $a_{n}$ 与 $a$ 的距离都小于 $\varepsilon$. 当然, 满足条件的 $N$ 不是唯一的, 如果 $N$ 对于某个 $\varepsilon$ 是合适的, 那么任何比 $N$ 大的整数对于这个 $\varepsilon$ 也是合适的. 一般来说, $N$ 依赖于 $\varepsilon$ 的选取, $\varepsilon$ 越小, 满足条件的最小 $N$ 就可能越大.

由于 $\varepsilon$ 的任意性, 对于常数 $c > 0$, 我们可将定义1.1.2中的不等式 $|a_{n} - a| < \varepsilon$ 换作 $|a_{n} - a| < c\varepsilon$, 也就是说, 定义中的 $|a_{n} - a| < \varepsilon$ 写成 $|a_{n} - a| < c\varepsilon$ 是等价的. 这在以后的有关分析证明中会很方便.

从定义 1.1.2 可以知道, 任意改变数列  $\{a_{n}\}$  的有限项并不会改变它的敛散性和极限. 因此, 一个数列的 “前面” 部分并不重要, 重要的是它的 “后面” 部分. 换句话说, 一个数列是否收敛或极限是多少与数列的前面有限多项没有关系.

我们常常用定义 1.1.2 来证明一个数列的极限存在, 并且数列收敛到某个数. 在证明中, 关键是对任意的正数 $\varepsilon$, 要找到一个满足条件的 $N$, 但这个 $N$ 只要找到就行, 不需要一定是最小的那个. 当然, 对于这个 $\varepsilon$, 其实只要考虑“任意小”的正数即可, 但要注意这个任意性, 而不是某个很小的数就可以.

#### 例 1.1.3 证明数列 $\left\{\frac{n}{n + 1}\right\}$ 收敛于1.

证明:因为 $|a_{n} - 1| = \frac{1}{n + 1}$，所以对于任意 $\varepsilon > 0$，取正整数 $N = \left[\frac{1}{\varepsilon}\right] + 1$ 则当 $n \geqslant N$ 时，有

$$
\boxed {| a _ {n} - 1 | = \frac {1}{n + 1} <   \frac {1}{n} \leqslant \frac {1}{N} = \frac {1}{\left[ \frac {1}{\varepsilon} \right] + 1} <   \frac {1}{\frac {1}{\varepsilon}} = \varepsilon .}
$$

因此, 数列  $\left\{\frac{n}{n+1}\right\}$  收敛于 1.

#### 例 1.1.4 证明数列 0.3, 0.33, 0.333,  $\cdots$ ,  $0.\underbrace{33\cdots3}_{\text{…}}$ ,  $\cdots$  的极限为  $\frac{1}{3}$ .

证明:设 $a_{n} = 0.\underbrace{33\cdots 3}_{n$ 个3},则

$$
\left| a _ {n} - \frac {1}{3} \right| = \left| 0. \underbrace {3 3 \cdots 3} _ {n \text {个} 3} - 0. 3 3 3 \dots 3 \dots \right| = \frac {1}{3 \times 1 0 ^ {n}}.
$$

§1.1 数列

所以, 对于任意 $\varepsilon > 0$, 可以取正整数 $N = \left[\frac{1}{\varepsilon}\right] + 1$, 当 $n \geqslant N$ 时,

$$
\left| a _ {n} - \frac {1}{3} \right| = \frac {1}{3 \times 1 0 ^ {n}} <   \frac {1}{1 0 ^ {n}} <   \frac {1}{n} \leqslant \frac {1}{N} <   \varepsilon .
$$

因此, 数列 0.3, 0.33, 0.333,  $\cdots$ ,  $0.\underbrace{33\cdots3}_{n\text{个}3}, \cdots$  的极限为  $\frac{1}{3}$ .

#### 例 1.1.5 证明数列 $\left\{\frac{1}{n^{\alpha}}\right\} (\alpha >0)$ 收敛于0.

证明:因为 $|a_{n} - 0| = \frac{1}{n^{\alpha}}$ ，所以对于任意 $\varepsilon > 0$ ，可以取到正整数 $N$ 使 $N > \frac{1}{\varepsilon^{\frac{1}{\alpha}}}$ ，此时 $N^{\alpha} > \frac{1}{\varepsilon}$. 因此，当 $n \geqslant N$ 时，$|a_{n} - 0| = \frac{1}{n^{\alpha}} \leqslant \frac{1}{N^{\alpha}} < \varepsilon$ ，即数列 $\left\{\frac{1}{n^{\alpha}}\right\}$ 收敛于0.

下面的定理是收敛数列的一个几何解释.

**定理 1.1.6** 数列 $\{a_{n}\}$ 收敛于 $a$ 当且仅当对于 $a$ 的任何 $\varepsilon$ 邻域 $U(a,\varepsilon)$, 除有限多项以外, $\{a_{n}\}$ 中其余的项都包含在 $U(a,\varepsilon)$ 内.

证明:设 $\lim_{n\to \infty}a_n = a,U(a,\varepsilon)$ 是 $a$ 的 $\varepsilon$ 邻域. 对此 $\varepsilon >0,\exists N > 0,$ 当$n\geqslant N$ 时，有

$$
| a _ {n} - a | <   \varepsilon ,
$$

即  $a_{n} \in U(a, \varepsilon)$ . 因此只有  $a_{1}, a_{2}, \cdots, a_{N-1}$  可能不在  $U(a, \varepsilon)$  内.

反过来, 假设 $a$ 的任意 $\varepsilon$ 邻域 $U(a, \varepsilon)$ 包含除有限多个以外的全部 $\{a_n\}$ 的项, 那么对于任意 $\varepsilon > 0$, 只有有限多项不在 $U(a, \varepsilon)$ 内, 记为 $a_{n_1}, a_{n_2}, \dots, a_{n_k}$. 取 $N = \max \{n_1, n_2, \dots, n_k\} + 1$, 则当 $n \geqslant N$ 时, $a_n \in U(a, \varepsilon)$, 即 $|a_n - a| < \varepsilon$, 所以

$$
\lim _ {n \to \infty} a _ {n} = a.
$$

#### 例 1.1.7 以下是几个常用的极限:

(1) 如果 $\alpha > 0$, 那么 $\lim_{n \to \infty} \frac{1}{n^{\alpha}} = 0$;

(2) 如果 $|a| < 1$, 那么 $\lim_{n \to \infty} a^n = 0$;

(3) 如果 $a > 0$, 那么 $\lim_{n\to \infty}\sqrt[n]{a} = 1$;

(4) $\lim_{n\to \infty}\sqrt[n]{n} = 1.$

证明: 上述极限中, (1) 已由例 1.1.5 证明; (2), (3) 的证明留给读者; 以下我们给出 (4) 的证明.

当 $n \geqslant 2$ 时, 有 $\sqrt[n]{n} > 1$. 记 $\sqrt[n]{n} = 1 + a_n (a_n > 0, n = 2, 3, \dots)$, 因此

$$
n = (1 + a _ {n}) ^ {n} = 1 + n a _ {n} + \frac {n (n - 1)}{2} a _ {n} ^ {2} + \dots + a _ {n} ^ {n} > \frac {n (n - 1)}{2} a _ {n} ^ {2},
$$

32

第1章

即

$$
0 <   a _ {n} <   \sqrt {\frac {2}{n - 1}}.
$$

令 $\sqrt{\frac{2}{n - 1}} < \varepsilon$, 得 $n > \frac{2}{\varepsilon^2} + 1$, 即只要 $n > \frac{2}{\varepsilon^2} + 1$, 就有 $a_n < \sqrt{\frac{2}{n - 1}} < \varepsilon$. 因此, $\forall \varepsilon > 0, \exists N = \max \left\{2, \left[\frac{2}{\varepsilon^2} + 1\right] + 1\right\}$, 当 $n \geqslant N$ 时,

$$
\left| \sqrt [ n ]{n} - 1 \right| = a _ {n} <   \sqrt {\frac {2}{n - 1}} <   \varepsilon .
$$

所以

$$
\lim _ {n \to \infty} \sqrt [ n ]{n} = 1.
$$

### 二、收敛数列的性质与极限的四则运算法则

![第1章图像：PDF 第 37 页，图像块 8](图片/第1章-P037-B08.png)

**定理 1.1.8** (唯一性) 如果数列  $\{a_{n}\}$  收敛, 那么其极限是唯一的.

**重难点讲解数列极限的性质**

证明: (反证法) 如果收敛数列 $\{a_{n}\}$ 有两个极限 $a, b$, 且 $a \neq b$, 即 $\lim_{n \to \infty} a_{n} = a$, $\lim_{n \to \infty} a_{n} = b$, 那么对 $\varepsilon = \frac{1}{2} |b - a| > 0$, 由 $\lim_{n \to \infty} a_{n} = a$ 知, 存在正整数 $N_{1}$, 当 $n \geqslant N_{1}$ 时,

$$
\left| a _ {n} - a \right| <   \varepsilon .\tag{①}
$$

由 $\lim_{n\to \infty}a_n = b$ 知, 存在正整数 $N_{2}$, 当 $n\geqslant N_{2}$ 时,

$$
\left| a _ {n} - b \right| <   \varepsilon .\tag{②}
$$

取 $N = \max \{N_{1}, N_{2}\}$, 则当 $n \geqslant N$ 时, ①式和②式同时成立. 因而

$$
| a - b | \leqslant | a - a _ {n} | + | a _ {n} - b | <   2 \varepsilon = | a - b |,
$$

矛盾, 从而可知收敛数列的极限是唯一的.

**定理 1.1.9** (有界性) 如果数列  $\{a_{n}\}$  收敛, 那么  $\{a_{n}\}$  有界, 即存在 M > 0, 使得对于所有的  $n \in N_{+}$ , 均有  $|a_{n}| \leqslant M$ .

证明:设 $\lim_{n\to \infty}a_n = a.$ 由数列极限的定义可知，对于 $\varepsilon = 1$ ，存在正整数$N$ ，当 $n\geqslant N$ 时，

$$
\left| a _ {n} - a \right| <   \varepsilon = 1,
$$

即

$$
\left| a _ {n} \right| \leqslant \left| a _ {n} - a \right| + \left| a \right| <   1 + \left| a \right|.
$$

取  $M = \max\left\{1 + |a|, |a_{1}|, |a_{2}|, \cdots, |a_{N-1}|\right\}$ ，则对于任意  $n \geqslant 1$ ，

$$
\left| a _ {n} \right| \leqslant M.
$$

收敛数列的有界性告诉我们, 若数列为无界数列, 则必是发散的. 例如斐波那契数列是无界的, 因此它是发散的.

**定理 1.1.10** (保号性) 如果  $\lim_{n\to\infty}a_{n}=a>0,$  那么  $\forall p\in(0,a),\exists N>0,$  当  $n\geqslant N$  时, 有  $a_{n}>p>0.$

证明: 对 $\varepsilon = a - p > 0$, 存在正整数 $N$, 当 $n \geqslant N$ 时, 有 $|a_{n} - a| < \varepsilon$. 即

$$
p <   a _ {n} <   2 a - p.
$$

因此, $\forall p\in (0,a),\exists N > 0$ ，当 $n\geqslant N$ 时，有 $a_{n} > p > 0$

在实际应用中, 经常取  $p = \frac{a}{3}$  或  $p = \frac{a}{2}$ .

同理, 我们可以得到

若 $\lim_{n\to \infty}a_n = a < 0$ ，则 $\forall -p\in (a,0)(p > 0),\exists N > 0,$ 当 $n\geqslant N$ 时，有$a_{n} <   - p <   0.$ 从而也可得到以下推论.

**推论 1.1.11** 若数列  $\{a_{n}\}$  满足: 当  $n \geqslant N \in N_{+}$  时,  $a_{n} \geqslant 0$ , 且  $\{a_{n}\}$  收敛于 a, 则  $a \geqslant 0$ .

值得一提的是, 上述推论中, 即使数列 $\{a_{n}\}$ 满足: 对所有的 $n \in \mathbb{N}, a_{n} > 0$ 且有极限 $a$, 也不能得出 $a > 0$. 例如: 数列 $\left\{\frac{1}{n}\right\}$ 满足 $\frac{1}{n} > 0$, 但其极限为零而非大于零.

#### 例 1.1.12 证明存在正整数 N, 当  $n \geqslant N$  时数列  $\left\{\frac{n^{3}}{c^{n}}\right\}(c > 1)$  严格单调减少.

证明: 设 $a_{n} = \frac{n^{3}}{\dot{c}^{n}}$, 记 $b_{n} = \frac{a_{n+1}}{a_{n}}$, 易得

$$
\lim _ {n \to \infty} b _ {n} = \lim _ {n \to \infty} \frac {1}{c} \left(1 + \frac {1}{n}\right) ^ {3} = \frac {1}{c} <   1,
$$

即

$$
\varliminf_ {n \to \infty} (b _ {n} - 1) = \frac {1}{c} - 1 <   0.
$$

由数列极限的保号性可得, 存在正整数 $N$, 当 $n \geqslant N$ 时, $b_{n} - 1 < 0$, 即 $a_{n+1} < a_{n}$, 所以数列 $\left\{\frac{n^3}{c^n}\right\}$ 严格单调减少.

从以上例题可以看出, 利用数列极限的定义来证明数列收敛与否或计算一个收敛数列的极限是非常不方便的. 它首先要求猜出极限值, 然后再证明这个值就是数列的极限. 为此, 我们需要给出一些求极限的方法和公式. 以下极限的四则运算法则, 将会给求极限带来许多方便.

34

第1章

**定理 1.1.13** (四则运算法则) 设  $\{a_{n}\}, \{b_{n}\}$  为收敛数列,  $c \in R$  为常数.
若  $\lim_{n\to\infty}a_{n}=a,\lim_{n\to\infty}b_{n}=b,$  则

(1) $\lim_{n\to \infty}(a_n + b_n) = \lim_{n\to \infty}a_n + \lim_{n\to \infty}b_n = a + b;$

(2) $\lim_{n\to \infty}ca_n = c\lim_{n\to \infty}a_n = ca;$

(3) $\lim_{n\to \infty}a_nb_n = \left(\lim_{n\to \infty}a_n\right)\left(\lim_{n\to \infty}b_n\right) = ab;$

(4) 如果 $b \neq 0$, 那么 $\lim_{n \to \infty} \frac{a_n}{b_n} = \frac{\lim_{n \to \infty} a_n}{\lim_{n \to \infty} b_n} = \frac{a}{b}$.

我们只给出 (1) 的证明, 其他证明请读者自己完成.

证明:因为 $\lim_{n\to \infty}a_n = a,\lim_{n\to \infty}b_n = b,$ 所以 $\forall \varepsilon >0,$ 存在正整数 $N_{1},N_{2},$

当 $n \geqslant N_{1}$ 时, 有 $|a_{n} - a| < \frac{\varepsilon}{2}$;

当 $n \geqslant N_{2}$ 时, 有 $|b_{n} - b| < \frac{\varepsilon}{2}$.

取 $N = \max \{N_1, N_2\}$, 则当 $n \geqslant N$ 时, 有

$$
\left| (a _ {n} + b _ {n}) - (a + b) \right| \leqslant | a _ {n} - a | + | b _ {n} - b | <   \varepsilon .
$$

所以

$$
\lim _ {n \to \infty} (a _ {n} + b _ {n}) = \lim _ {n \to \infty} a _ {n} + \lim _ {n \to \infty} b _ {n} = a + b.
$$

由上述数列极限的四则运算法则可知, 若 $\lim_{n\to \infty}a_n = a,$ 则 $\forall k\in \mathbb{N}_{+}$, 有

$$
\lim _ {n \to \infty} (a _ {n}) ^ {k} = \lim _ {n \to \infty} a _ {n} \cdot \lim _ {n \to \infty} a _ {n} \cdot \dots \cdot \lim _ {n \to \infty} a _ {n} = a ^ {k}.
$$

#### 例 1.1.14 计算下列极限:

(1) $\lim_{n\to \infty}\left(\frac{n - 1}{2n + 7}\right)^4;$ (2) $\lim_{n\to \infty}\frac{\mathrm{e}^n - 4^{n + 1}}{2\cdot 4^n + 5};$ (3) $\lim_{n\to \infty}\sqrt[n]{2n}.$

解:(1) $\lim_{n\to \infty}\left(\frac{n - 1}{2n + 7}\right)^4 = \left(\lim_{n\to \infty}\frac{n - 1}{2n + 7}\right)^4$ $= \left(\lim_{n\to \infty}\frac{1 - \frac{1}{n}}{2 + \frac{7}{n}}\right)^4$ $= \left[\frac{\lim_{n\to\infty}\left(1 - \frac{1}{n}\right)}{\lim_{n\to\infty}\left(2 + \frac{7}{n}\right)}\right]^4$

§1.1 数列

第1章

$$
\begin{array}{l} = \left(\frac {1 - \lim _ {n \to \infty} \frac {1}{n}}{2 + 7 \lim _ {n \to \infty} \frac {1}{n}}\right) ^ {4} \\ = \left(\frac {1}{2}\right) ^ {4} = \frac {1}{1 6}. \end{array}
$$

$$
\lim _ {n \to \infty} \frac {\mathrm{e} ^ {n} - 4 ^ {n + 1}}{2 \cdot 4 ^ {n} + 5} = \lim _ {n \to \infty} \frac {\left(\frac {\mathrm{e}}{4}\right) ^ {n} - 4}{2 + 5 \cdot \frac {1}{4 ^ {n}}} = \frac {\lim _ {n \to \infty} \left(\frac {\mathrm{e}}{4}\right) ^ {n} - 4}{2 + 5 \lim _ {n \to \infty} \left(\frac {1}{4}\right) ^ {n}} = - 2. \tag {2}
$$

$$
\lim _ {n \to \infty} \sqrt [ n ]{2 n} = \lim _ {n \to \infty} \left(\sqrt [ n ]{2} \cdot \sqrt [ n ]{n}\right) = \left(\lim _ {n \to \infty} \sqrt [ n ]{2}\right) \cdot \left(\lim _ {n \to \infty} \sqrt [ n ]{n}\right) = 1.
$$

**定理 1.1.15** (夹逼定理) 设数列 $\{a_{n}\}, \{b_{n}\}, \{c_{n}\}$ 满足当 $n \geqslant N_{0} \in \mathbb{N}_{+}$ 时, 有 $b_{n} \leqslant a_{n} \leqslant c_{n}$, 并且 $\lim_{n \to \infty} b_{n} = \lim_{n \to \infty} c_{n} = a$, 则数列 $\{a_{n}\}$ 也是收敛的, 并且 $\lim_{n \to \infty} a_{n} = a$.

证明: $\forall \varepsilon > 0$, 因为 $\lim_{n \to \infty} b_n = a$, 所以 $\exists N_1 \in \mathbb{N}_+$, 当 $n \geqslant N_1$ 时, 有

$$
\left| b _ {n} - a \right| <   \varepsilon ,
$$

即

$$
a - \varepsilon <   b _ {n} <   a + \varepsilon .
$$

又因为 $\lim_{n\to \infty}c_n = a,$ 所以 $\exists N_2\in \mathbb{N}_+$ ，当 $n\geqslant N_2$ 时，有

$$
| c _ {n} - a | <   \varepsilon ,
$$

即

$$
a - \varepsilon <   c _ {n} <   a + \varepsilon .
$$

记 $N = \max \{N_0, N_1, N_2\}$, 则当 $n \geqslant N$ 时,

$$
a - \varepsilon <   b _ {n} \leqslant a _ {n} \leqslant c _ {n} <   a + \varepsilon,
$$

即

$$
\left| a _ {n} - a \right| <   \varepsilon .
$$

所以数列 $\{a_{n}\}$ 也是收敛的, 并且 $\lim_{n\to \infty}a_n = a$.

#### 例 1.1.16 求 $\lim_{n\to \infty}\frac{\sin n\alpha}{n},\alpha \in \mathbb{R}.$

解:注意到 $-\frac{1}{n} \leqslant \frac{\sin n\alpha}{n} \leqslant \frac{1}{n}$, 且易得

$$
\lim _ {n \to \infty} \left(- \frac {1}{n}\right) = \lim _ {n \to \infty} \frac {1}{n} = 0.
$$

36

由夹逼定理可得

$$
\lim _ {n \to \infty} \frac {\sin n \alpha}{n} = 0.
$$

#### 例 1.1.17 求 $\lim_{n\to \infty}\left(\sqrt{n^2 + n} -n\right)$

解:因为

$$
\frac {n}{2 n + 1} = \frac {n}{\sqrt {n ^ {2} + 2 n + 1} + n} \leqslant \sqrt {n ^ {2} + n} - n = \frac {n}{\sqrt {n ^ {2} + n} + n} \leqslant \frac {n}{2 n} = \frac {1}{2},
$$

且

$$
\lim _ {n \to \infty} \frac {n}{2 n + 1} = \lim _ {n \to \infty} \frac {1}{2 + \frac {1}{n}} = \frac {1}{2},
$$

所以根据数列极限的夹逼定理可得

$$
\varliminf_ {n \to \infty} \left(\sqrt {n ^ {2} + n} - n\right) = \frac {1}{2}.
$$

#### 例 1.1.18 求 $\lim_{n\to \infty}\left(\frac{1}{n^2 + 1} +\frac{2}{n^2 + 2} +\dots +\frac{n}{n^2 + n}\right)$.

解:因为

$$
\begin{array}{r l} \frac {1}{2} & = \frac {1 + 2 + 3 + \cdots + n}{n ^ {2} + n} \leqslant \frac {1}{n ^ {2} + 1} + \frac {2}{n ^ {2} + 2} + \dots + \frac {n}{n ^ {2} + n}, \\ & \leqslant \frac {1 + 2 + 3 + \cdots + n}{n ^ {2}} = \frac {1}{2} \left(1 + \frac {1}{n}\right), \end{array}
$$

日

$$
\lim _ {n \to \infty} \frac {1}{2} \left(1 + \frac {1}{n}\right) = \frac {1}{2},
$$

所以根据数列极限的夹逼定理可得

$$
\lim _ {n \to \infty} \left(\frac {1}{n ^ {2} + 1} + \frac {2}{n ^ {2} + 2} + \dots + \frac {n}{n ^ {2} + n}\right) = \frac {1}{2}.
$$

### 三、无穷大数列

有一类发散数列有着特殊的性质, 我们称其为无穷大数列.

**定义 1.1.19** 设 $\{a_{n}\}$ 是 $\mathbb{R}$ 中的一个数列, 如果 $\forall M > 0, \exists N \in \mathbb{N}_{+}$, 当 $n \geqslant N$ 时, $|a_{n}| > M$, 那么称 $\{a_{n}\}$ 为无穷大数列, 或称 $\{a_{n}\}$ 趋于 $\infty$, 记为 $\lim_{n \to \infty} a_{n} = \infty$.

特别地, 如果 $\forall M > 0, \exists N \in \mathbb{N}_{+}$, 当 $n \geqslant N$ 时, $a_{n} > M$ (或者 $a_{n} < -M$), 就称 $\{a_{n}\}$ 趋于 $+\infty$ (或者 $-\infty$), 记为

$$
\lim _ {n \to \infty} a _ {n} = + \infty (\text {或者} \lim _ {n \to \infty} a _ {n} = - \infty).
$$

§1.1 数列

容易证明, 数列 $\{n\}$ 趋于 $+\infty$, 数列 $\{-n\}$ 趋于 $-\infty$, 而数列 $\{(-1)^{n-1} \cdot n\}$ 趋于 $\infty$.

**定理 1.1.20** 数列 $\{a_{n}\}$ 为无穷大数列当且仅当 $\lim_{n\to \infty}\frac{1}{a_n} = 0.$

从无穷大数列的定义可知, 无穷大数列必为无界数列. 但要注意的是, 无界数列不一定是无穷大数列. 例如, 数列

$$
0, 2, 0, 4, \dots , \frac {1 + (- 1) ^ {n}}{2} n, \dots
$$

是一个无界数列, 但它显然不是无穷大数列.

无穷大数列是发散的, 但它是一种特殊的发散情况, 有时我们习惯地说无穷大数列的极限为无穷大.

## §1.2 确界原理

实数集是由有理数集和无理数集“合并”而成的. 实数有一些特殊的性质, 例如任何两个实数都可以比较大小; 任何两个不同的实数之间, 既有无穷多个有理数, 也有无穷多个无理数; 还有一些运算性质等. 下面介绍实数的一个重要原理, 即所谓的确界原理, 这个确界原理也是实数连续性的一种表现.

**定义 1.2.1** 设 S 是一个由实数组成的非空集合.

(1) 如果存在 $M \in \mathbb{R}$ 使得

$$
\forall x \in S, \quad x \leqslant M (\text {或} x \geqslant M),
$$

那么称 $S$ 有上界 (或有下界), 称 $M$ 为 $S$ 的一个上界 (或下界).

如果 $S$ 既有上界又有下界, 那么称 $S$ 为有界集合, 否则称为无界集合.

(2) 如果 (i) $M \in \mathbb{R}$ 是 $S$ 的一个上界 (或下界); (ii) 任何小 (大) 于 $M$ 的实数都不是 $S$ 的上界 (或下界), 那么称 $M$ 是 $S$ 的上确界 (或下确界), 我们分别用 $\sup S$ 和 $\inf S$ 表示 $S$ 的上确界和下确界.

(3) 如果 $\sup S \in S$ (或 $\inf S \in S$), 那么分别称为 $S$ 的最大元 (或最小元), 记为 $\max S$ (或 $\min S$).

【注1】非空实数集的上(下)界不是唯一的. 事实上, 如果 $M_0$ 是 $S$ 的上界, 那么任何 $M > M_0$ 都是 $S$ 的上界; 如果 $m_0$ 是 $S$ 的下界, 那么任何 $m < m_0$ 都是 $S$ 的下界. 但非空实数集的上(下)确界是唯一的. 因为假设 $M_1, M_2$ 为 $S$ 的上确界, 如果 $M_1 < M_2$, 从上确界的定义知 $M_1$ 不是 $S$ 的上界, 故 $M_1$ 不是 $S$ 的上确界, 矛盾, 所以上确界是唯一的. 同理可得下确界是唯一的.

【注2】上确界和下确界的记号分别来自英文 supremum 和 infimum. 实数集 $S$ 若有上界, 则其上确界即是 $S$ 的最小的上界; 若 $S$ 有下界, 则其下确界即是 $S$ 的最大的下界. 最大元和最小元的符号分别来源于英文 maximum 和 minimum.

【注3】以下是非空实数集 $S$ 的上确界和下确界的等价定义:

(1) 实数 $M$ 是 $S$ 的上确界当且仅当满足

①  $\forall x \in S, x \leqslant M;$

② $\forall \varepsilon > 0$, 存在 $x_0 \in S$, 使得 $x_0 > M - \varepsilon$.

(2) 实数 $m$ 是 $S$ 的下确界当且仅当满足

①  $\forall x \in S, x \geqslant m;$

② $\forall \varepsilon > 0$, 存在 $x_0 \in S$, 使得 $x_0 < m + \varepsilon$.

#### 例 1.2.2 设 $S = \mathbb{R}_{+}$. $S$ 没有上界, 任何 $M < 0$ 是 $S$ 的下界, 0 是 $S$ 的下确界, 但 0 不是 $S$ 的最小元, 因为 $0 \notin \mathbb{R}_{+}$.

#### 例 1.2.3 设 $S = \{x \in \mathbb{R} | -1 \leqslant x < 1\}$. $S$ 是有界集, 任何 $M_1 \leqslant -1$ 是 $S$ 的下界, $-1$ 是 $S$ 的下确界, 同时也是 $S$ 的最小元; 任何 $M_2 \geqslant 1$ 是 $S$ 的上界, $1$ 是 $S$ 的上确界, 但 $1$ 不是 $S$ 的最大元.

显然, 若实数集 $S$ 的元素只有有限个, 则其上确界即为 $S$ 中最大的那个元素的值, 下确界即为 $S$ 中最小的那个元素的值. 若实数集 $S$ 的元素有无穷多个, 则即使 $S$ 是有界集, 也不一定有最小的数或最大的数. 例如, 开区间 $(0,1)$ 内的所有实数组成的集合是一个有界集, 但没有最小的数和最大的数. 我们已经知道, 一个有上界的集合, 其上界有无穷多个, 从而所有上界组成的集合是一个无穷集; 同样, 一个有下界的集合的所有下界组成的集合也是一个无穷集. 下面的确界原理告诉我们, 这两个无穷集分别有最小元和最大元.

**定理 1.2.4** (确界原理) 任何 R 的有上 (下) 界的非空子集都有上 (下) 确界.

确界原理告诉我们: 若 $S$ 是 $\mathbb{R}$ 的非空子集, 而且 $S$ 有上界 (或下界), 则存在 $M \in \mathbb{R}$ (或 $m \in \mathbb{R}$) 使得 $M = \sup S$ (或 $m = \inf S$).

由收敛数列的有界性知, 收敛数列必为有界数列, 那么有界数列是否一定收敛呢? 回答是否定的. 例如数列 $\{(-1)^n\}$ 显然是有界的, 但没有极限, 是发散的. 但对单调数列, 情况就不一样了.

#### 例 1.2.5 (1) 数列  $\left\{\frac{n+2}{n+1}\right\}$  为严格单调减少且有界的数列, 易知此数列收敛到 1;

(2) 设数列  $\{S_{n}\}$ ，其中  $S_{n}=1+\frac{1}{2^{2}}+\frac{1}{3^{2}}+\cdots+\frac{1}{n^{2}}, n=1,2,3,\cdots$ ，显然此数列为严格单调增加数列。又因为

$$
\begin{array}{r l} & 0 <   S _ {n} <   1 + \frac {1}{1 \cdot 2} + \frac {1}{2 \cdot 3} + \dots + \frac {1}{(n - 1) n} \\ & \quad = 1 + \left(1 - \frac {1}{2}\right) + \left(\frac {1}{2} - \frac {1}{3}\right) + \dots + \left(\frac {1}{n - 1} - \frac {1}{n}\right) \\ & \quad <   2 - \frac {1}{n} <   2, \end{array}
$$

§1.2 确界原理

所以 $\{S_n\}$ 有界. 下面的定理1.2.6阐明了单调有界数列必收敛, 所以此数列是收敛的. 但是要求出此数列 $\{S_n\}$ 的极限却并非易事.

**定理 1.2.6** (单调收敛准则) 若单调数列  $\{a_{n}\}$  有界, 则  $\{a_{n}\}$  必收敛.

证明:不妨设  $\{a_{n}\}$  单调增加并且有界，即有上界，由确界原理知必有上确界。记 a 为有界集  $S=\{a_{1},a_{2},\cdots,a_{n},\cdots\}$  的上确界，则  $\forall\varepsilon>0,a-\varepsilon$  不是 S 的上确界，所以存在正整数 N 使得

$$
a - \varepsilon <   a _ {N} \leqslant a.
$$

因为 $\{a_{n}\}$ 单调增加, 所以对于任何 $n \geqslant N$, 有

$$
a - \varepsilon <   a _ {N} \leqslant a _ {n} \leqslant a <   a + \varepsilon ,
$$

即 $\forall \varepsilon > 0, \exists N \in \mathbb{N}_{+}$, 当 $n \geqslant N$ 时, 有 $|a_{n} - a| < \varepsilon$. 因此 $\lim_{n \to \infty} a_{n} = a$.

由上面证明可知, 单调增加数列  $\{a_{n}\}$  收敛于数集  $\{a_{1}, a_{2}, \cdots, a_{n}, \cdots\}$  的上确界. 同样, 如果  $\{a_{n}\}$  单调减少且有界, 即有下界, 类似地可证明数列  $\{a_{n}\}$  收敛于  $\{a_{1}, a_{2}, \cdots, a_{n}, \cdots\}$  的下确界.

【注 4】要证明单调增加数列 $\{a_{n}\}$ 收敛, 我们只要证明 $\{a_{n}\}$ 有上界即可, 因为 $a_{1}$ 明显是 $\{a_{n}\}$ 的下界. 同样, 要证明单调减少数列 $\{a_{n}\}$ 收敛, 我们只要证明 $\{a_{n}\}$ 有下界即可, 因为 $a_{1}$ 明显是 $\{a_{n}\}$ 的上界.

【注5】因为数列收敛与否和数列的前面有限项没有关系, 所以数列的单调性不需要从一开始就满足, 只要存在 $N \in \mathbb{N}_{+}$ 使数列 $\{a_{n}\}_{n=N}^{\infty}$ 是单调的就可以了.

单调收敛准则是判断一个数列收敛的一种重要手段, 但求出一个数列的极限, 往往仍是一件不太容易的事. 但当数列满足一个递推关系时, 如果此数列收敛, 那么往往可以通过等式两边取极限来得到极限值, 请见例 1.2.11—1.2.13.

#### 例 1.2.7 证明: 数列  $\{S_{n}\}$  收敛, 其中

$$
S _ {n} = 1 + \frac {1}{1 !} + \frac {1}{2 !} + \frac {1}{3 !} + \dots + \frac {1}{n !},
$$

且有

$$
2 <   \lim _ {n \to \infty} S _ {n} \leqslant 3.
$$

证明: 显然 $\{S_{n}\}$ 是严格单调增加的. 由单调收敛准则, 只需证明 $\{S_{n}\}$ 有上界.

对于 $n \geqslant 2, n! \geqslant 2^{n-1}$, 因此当 $n > 3$ 时, $S_n > S_2 = \frac{5}{2}$,

$$
S _ {n} = 1 + \frac {1}{1 !} + \frac {1}{2 !} + \frac {1}{3 !} + \dots + \frac {1}{n !} \leqslant 1 + 1 + \frac {1}{2} + \frac {1}{2 ^ {2}} + \dots + \frac {1}{2 ^ {n - 1}} <   3.
$$

所以数列 $\{S_n\}$ 单调增加且有上界, 从而数列 $\{S_n\}$ 收敛, 并且

$$
2 <   \frac {5}{2} <   \lim _ {n \to \infty} S _ {n} \leqslant 3.
$$

40

第1章

#### 例 1.2.8 证明数列  $\left\{\left(1+\frac{1}{n}\right)^{n}\right\}$  收敛, 且  $2 < \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^{n} \leqslant 3$ .

证明:记 $a_{n} = \left(1 + \frac{1}{n}\right)^{n}$，我们证明 $\{a_{n}\}$ 严格单调增加且有上界，然后由单调收敛准则得到 $\{a_{n}\}$ 收敛.

根据二项式展开, 有

$$
\begin{array}{l} a _ {n} = \left(1 + \frac {1}{n}\right) ^ {n} \\ \quad = 1 + \frac {n !}{(n - 1) !} \frac {1}{n} + \frac {n !}{2 ! (n - 2) !} \left(\frac {1}{n}\right) ^ {2} + \dots + \\ \quad \frac {n !}{k ! (n - k) !} \left(\frac {1}{n}\right) ^ {k} + \dots + \frac {n !}{n !} \left(\frac {1}{n}\right) ^ {n} \\ \quad = 1 + 1 + \frac {1}{2 !} \left[ \frac {n (n - 1)}{n ^ {2}} \right] + \dots + \frac {1}{k !} \left[ \frac {n (n - 1) \cdots (n - k + 1)}{n ^ {k}} \right] + \frac {n !}{n !} \left(\frac {1}{n}\right) ^ {n} \\ \quad = 1 + 1 + \frac {1}{2 !} \left(1 - \frac {1}{n}\right) + \dots + \frac {1}{k !} \left(1 - \frac {1}{n}\right) \dots \left(1 - \frac {k - 1}{n}\right) + \dots + \\ \quad \frac {1}{n !} \left(1 - \frac {1}{n}\right) \left(1 - \frac {2}{n}\right) \dots \left(1 - \frac {n - 1}{n}\right), \\ a _ {n + 1} = \left(1 + \frac {1}{n + 1}\right) ^ {n + 1} \\ \quad = 1 + 1 + \frac {1}{2 !} \left(1 - \frac {1}{n + 1}\right) + \dots + \frac {1}{k !} \left(1 - \frac {1}{n + 1}\right) \dots \left(1 - \frac {k - 1}{n + 1}\right) + \dots + \\ \quad \frac {1}{n !} \left(1 - \frac {1}{n + 1}\right) \left(1 - \frac {2}{n + 1}\right) \dots \left(1 - \frac {n - 1}{n + 1}\right) + \\ \quad \frac {1}{(n + 1) !} \left(1 - \frac {1}{n + 1}\right) \left(1 - \frac {2}{n + 1}\right) \dots \left(1 - \frac {n}{n + 1}\right). \end{array}
$$

比较 $a_{n + 1}$ 和 $a_{n}$ 的展开式各项, 立即可以看出, 对于全部 $n \geqslant 1$, 有 $a_{n} < a_{n + 1}$, 所以 $\{a_{n}\}$ 严格单调增加.

另外, 由上述展开式和例 1.2.7 易知, 当 $n \geqslant 2$ 时,

$$
2 <   \frac {9}{4} = a _ {2} \leqslant a _ {n} \leqslant 1 + \frac {1}{1 !} + \frac {1}{2 !} + \dots + \frac {1}{k !} + \dots + \frac {1}{n !} <   3.
$$

因此数列 $\left\{\left(1 + \frac{1}{n}\right)^n\right\}$ 收敛, 且 $2 < \lim_{n\to \infty}\left(1 + \frac{1}{n}\right)^n \leqslant 3.$

我们记这个极限为 $\mathrm{e} = \lim_{n\to \infty}\left(1 + \frac{1}{n}\right)^n$ ，称为自然对数的底.可以证明e

§1.2 确界原理

是一个无理数, 其值为 $e = 2.7182818284590\cdots$.

#### 例 1.2.9 证明:  $\lim_{n\to\infty}\left(1+\frac{1}{1!}+\frac{1}{2!}+\cdots+\frac{1}{n!}\right)=\lim_{n\to\infty}\left(1+\frac{1}{n}\right)^{n}=e.$

证明:记 $a_{n} = \left(1 + \frac{1}{n}\right)^{n}, S_{n} = 1 + \frac{1}{1!} + \frac{1}{2!} + \dots + \frac{1}{n!}$，则 $\lim_{n\to \infty}a_n = \mathrm{e}$

固定 $k \in \mathbb{N}_{+}$, 对于全部 $n \geqslant k$, 从例1.2.8的证明中的展开式可知

$$
a _ {n} \geqslant 1 + 1 + \frac {1}{2 !} \left(1 - \frac {1}{n}\right) + \dots + \frac {1}{k !} \left(1 - \frac {1}{n}\right) \left(1 - \frac {2}{n}\right) \dots \left(1 - \frac {k - 1}{n}\right).
$$

当 $n\to \infty$ 时，得到

$$
\lim _ {n \to \infty} a _ {n} \geqslant 1 + \frac {1}{1 !} + \frac {1}{2 !} + \dots + \frac {1}{k !} = S _ {k}.
$$

从而对任意正整数 $n$ ，有 $S_{n}\leqslant \mathrm{e}$

由例1.2.8的证明可得

$$
a _ {n} \leqslant S _ {n}.
$$

所以对于全部 $n \in \mathbb{N}_{+}$, 有

$$
a _ {n} \leqslant S _ {n} \leqslant \lim _ {n \to \infty} a _ {n} = \mathrm{e}.
$$

因此, 由数列极限的夹逼定理有

$$
\lim _ {n \to \infty} S _ {n} = \lim _ {n \to \infty} a _ {n} = \lim _ {n \to \infty} \left(1 + \frac {1}{n}\right) ^ {n} = \mathrm{e}.
$$

我们可以用 e 的定义来计算一些极限.

#### 例 1.2.10 计算极限 $\lim_{n\to \infty}\left(1 + \frac{1}{n + 3}\right)^{2n}$

$$
\begin{array}{r l} \lim _ {n \to \infty} \left(1 + \frac {1}{n + 3}\right) ^ {2 n} & = \lim _ {n \to \infty} \left(1 + \frac {1}{n + 3}\right) ^ {2 (n + 3) - 6} \\ & = \left[ \lim _ {n \to \infty} \left(1 + \frac {1}{n + 3}\right) ^ {n + 3} \right] ^ {2} \cdot \lim _ {n \to \infty} \left(1 + \frac {1}{n + 3}\right) ^ {- 6} \\ & = \mathrm{e} ^ {2}. \end{array}
$$

#### 例 1.2.11 数列  $\{a_{n}\}$  由递推公式  $a_{1}=1, a_{n+1}=\sqrt{3a_{n}}$  来定义, 试证明  $\{a_{n}\}$  收敛, 并求它的极限.

解: (a) 显然 $a_{n} > 0, a_{1} = 1 < 3, a_{2} = \sqrt{3} < 3$. 用数学归纳法, 假设 $a_{n} < 3$, 则有 $a_{n+1} = \sqrt{3a_{n}} < \sqrt{3 \cdot 3} = 3$, 所以由归纳假设得 $\{a_{n}\}$ 有上界.

又因为 $a_{n+1} - a_n = \sqrt{3a_n} - a_n = \frac{(3 - a_n)a_n}{\sqrt{3a_n} + a_n} > 0 (n = 1, 2, \cdots)$, 所以数列 $\{a_n\}$ 单调增加. 由单调收敛准则, 数列 $\{a_n\}$ 收敛.

42

第1章

(b) 记 $\{a_{n}\}$ 的极限为 $a$. 从 $a_{n+1} = \sqrt{3a_{n}}$ 得 $a_{n+1}^{2} = 3a_{n}$. 注意到 $\lim_{n \to \infty} a_{n+1} = \lim_{n \to \infty} a_{n}$, 有 $a^{2} = 3a$. 因此, $a = 0$ 或 $a = 3$. 但是 $a_{n} \geqslant a_{1} = 1$, 因此 0 不可能是 $\{a_{n}\}$ 的极限, 所以 $\{a_{n}\}$ 的极限是 3.

#### 例 1.2.12 对于 $a \in \mathbb{R}$, 证明: $\lim_{n \to \infty} \frac{a^n}{n!} = 0$.

证明:我们先证明 $\lim_{n\to \infty}\frac{|a|^n}{n!} = 0.$

当 $a = 0$ 时，显然成立.

当 $a \neq 0$ 时, 令 $b_{n} = \frac{|a|^{n}}{n!}$, 则当 $n \geqslant |a|$ 时, $\frac{b_{n+1}}{b_n} = \frac{|a|}{n+1} < 1$. 所以, 除开始的有限多项外, $\{b_n\}$ 单调减少. 显然 0 是 $\{b_n\}$ 的下界, 由单调收敛准则, $\{b_n\}$ 收敛.

设 $\lim_{n\to \infty}b_n = b,$ 注意到 $b_{n + 1} = \frac{|a|}{n + 1} b_n$ 当 $n\to \infty$ 时，有 $b = 0\cdot b = 0$ ，即$\lim_{n\to \infty}\frac{|a|^n}{n!} = 0.$ 由不等式 $-\frac{|a|^n}{n!}\leqslant \frac{a^n}{n!}\leqslant \frac{|a|^n}{n!}$ 和数列极限的夹逼定理可得

$$
\lim _ {n \to \infty} \frac {a ^ {n}}{n !} = 0.
$$

#### 例 1.2.13 已知数列  $\{u_{n}\}$  满足:  $u_{1} > 0, u_{n+1} = 3 + \frac{4}{u_{n}} (n = 1, 2, \cdots)$ ，证明数列  $\{u_{n}\}$  收敛并求其极限.

【分析】由已知条件易知 $u_{n} > 3 (n = 2,3,\dots)$, 如果 $\lim_{n\to \infty}u_n$ 存在, 记其极限为 $A(>0)$, 等式 $u_{n + 1} = 3 + \frac{4}{u_n}$ 两边取极限, 有 $A = 3 + \frac{4}{A}$. 因此

$$
A = 4 \text {或} A = - 1 (\text {舍去}).
$$

解: (方法一) 先证明极限  $\lim_{n\to\infty}u_n$  存在. 其实, 数列  $\{u_n\}$  并不是单调数列, 其单调性与数列第一项  $u_1$  的取值有关.

$$
u _ {n + 1} - 4 = \frac {4 - u _ {n}}{u _ {n}} = \frac {4 - \left(3 + \frac {4}{u _ {n - 1}}\right)}{3 + \frac {4}{u _ {n - 1}}} = \frac {u _ {n - 1} - 4}{3 u _ {n - 1} + 4}.
$$

① 若 $u_{1} > 4$ ，则 $u_{2n + 1} > 4, n = 1,2,\dots$ ，即 $\{u_{2n + 1}\}$ 有下界.

② 若 $u_{1} < 4$ ，则 $u_{2n + 1} < 4, n = 1,2,\dots$ ，即 $\{u_{2n + 1}\}$ 有上界.

因为 $u_{n + 1} - u_{n - 1} = \frac{-3(u_{n - 1} + 1)(u_{n - 1} - 4)}{3u_{n - 1} + 4}$ ，所以

若 $u_{1} > 4$ ，则 $\{u_{2n + 1}\}$ 单调减少，且由①知 $\{u_{2n + 1}\}$ 有下界，故 $\{u_{2n + 1}\}$ 收敛.

§1.2 确界原理

44

若 $u_{1} < 4$, 则 $\{u_{2n+1}\}$ 单调增加, 且由②知 $\{u_{2n+1}\}$ 有上界, 故 $\{u_{2n+1}\}$ 收敛.

若 $u_{1} = 4$ ，由递推关系即知 $u_{n} = 4 (n = 1,2,\dots)$

因此， $\lim_{n\to \infty}u_{2n + 1} = 4.$ 又因为 $u_{2n} = 3 + \frac{4}{u_{2n - 1}}$ ，所以 $\lim_{n\to \infty}u_{2n} = 4.$

总之， $\lim_{n\to \infty}u_n = 4.$

(方法二) 由已知条件易知 $u_{n} > 3, n = 2,3,\dots$ ，所以

$$
\begin{array}{r l} 0 <   | u _ {n + 1} - 4 | & = \frac {| u _ {n} - 4 |}{u _ {n}} <   \frac {1}{3} | u _ {n} - 4 | \\ & <   \frac {1}{3 ^ {2}} | u _ {n - 1} - 4 | <   \dots <   \frac {1}{3 ^ {n}} | u _ {1} - 4 |. \end{array}
$$

因为 $|u_{1} - 4|$ 为一个常数, 所以 $\lim_{n\to \infty}\frac{1}{3^{n}} |u_{1} - 4| = 0$, 由夹逼定理知 $\lim_{n\to \infty}u_n = 4$.

## §1.3 柯西准则

在数列收敛的定义中, 我们要知道 (或猜到) 这个数列的极限, 才能证明其收敛, 这在具体应用时非常不方便. 有时候我们只关心这个数列是否收敛而不需知道它的极限, 况且事实上有些收敛数列的极限是无法人工计算的. 柯西准则很好地解决了这方面的问题. 在介绍柯西准则之前, 我们先来介绍子数列的概念.

**定义 1.3.1** 设 $\{a_{n}\}$ 是 $\mathbb{R}$ 中的一个数列, $\{n_k\}$ 是 $\mathbb{N}_{+}$ 的无限子集, 且满足

$$
n _ {1} <   n _ {2} <   \dots <   n _ {k} <   \dots ,
$$

称  $\{a_{n_{k}}\}$  是  $\{a_{n}\}$  的一个子数列或子列.

例如, 数列 $\left\{\frac{1}{4n - 1}\right\}$ 为数列 $\left\{\frac{1}{n}\right\}$ 的一个子列. 事实上, 子列就是原数列按顺序选出无穷多项组成的新数列. 当然, 按以上定义, 数列本身也是其子列.

**定理 1.3.2** 数列 $\{a_{n}\}$ 收敛的充要条件是 $\{a_{n}\}$ 的任一子列都收敛且收敛于相同的极限.

证明: 因为 $\{a_{n}\}$ 本身是 $\{a_{n}\}$ 的一个子列, 所以充分性是显然的. 下面证明必要性.

设 $\lim_{n\to \infty}a_n = a,$ 要证对于任何子列 $\{a_{n_k}\}$ ， $\lim_{n\to \infty}a_{n_k} = a.$

对于任意 $\varepsilon > 0$, 由 $\lim_{n \to \infty} a_n = a$, 存在正整数 $N$, 当 $n \geqslant N$ 时, 有

$$
\left| a _ {n} - a \right| <   \varepsilon .
$$

由于 $n_1 < n_2 < \dots < n_j < \dots$, 显然有 $j \leqslant n_j$ 对于所有 $j \geqslant 1$ 成立. 因此当 $k \geqslant N$ 时, $n_k \geqslant k \geqslant N$, 有 $|a_{n_k} - a| < \varepsilon$, 即 $\lim_{n \to \infty} a_{n_k} = a$.

第1章

**定理 1.3.2** 常被用来证明数列的发散性: (1) 如果我们找到  $\{a_{n}\}$  的一个子列是发散的, 那么  $\{a_{n}\}$  必然是发散的, 例如  $a_{n} = \frac{1 + (-1)^{n}}{2} \cdot n, \{a_{2n}\}$  无界, 所以发散, 因此  $\{a_{n}\}$  是发散的; (2) 如果我们找到  $\{a_{n}\}$  的两个子列, 一个收敛于 a, 另一个收敛于 b, 而且  $a \neq b$ , 那么  $\{a_{n}\}$  必然是发散的, 例如  $a_{n} = \sin \frac{n\pi}{2}, \{a_{4n}\}$  收敛于 0,  $\{a_{4n+1}\}$  收敛于 1, 因此  $\{a_{n}\}$  是发散的.

前面我们已经知道, 有界数列不一定收敛, 但有界数列一定有收敛的子列, 这就是以下的波尔查诺 $^{①}$ -魏尔斯特拉斯 $^{②}$ 定理, 其证明可见一般的数学分析教材, 这里我们不加证明.

**定理 1.3.3** (波尔查诺-魏尔斯特拉斯定理) 设  $\{a_{n}\}$  是 R 中的一个有界数列, 则数列  $\{a_{n}\}$  中存在收敛的子列.

**定义 1.3.4** 设  $\{a_{n}\}$  是 R 中一个数列. 若对于任意  $\varepsilon > 0$ , 存在正整数 N, 当  $m, n \geqslant N$  时,  $|a_{m} - a_{n}| < \varepsilon$ , 则称  $\{a_{n}\}$  是柯西数列, 简称柯西列.

**定理 1.3.5** (柯西准则) 设  $\{a_{n}\}$  是 R 中的一个数列, 则  $\{a_{n}\}$  收敛当且仅当  $\{a_{n}\}$  是柯西数列.

证明:设 $\lim_{n\to \infty}a_n = a,$ 则对于任意 $\varepsilon >0$ ，存在正整数 $N$ ，当 $n\geqslant N$ 时，

$$
\boxed {| a _ {n} - a | <   \frac {1}{2} \varepsilon .}
$$

因此当 $m, n \geqslant N$ 时, 同时有 $|a_{n} - a| < \frac{1}{2}\varepsilon$ 和 $|a_{m} - a| < \frac{1}{2}\varepsilon$, 从而

$$
\left| a _ {m} - a _ {n} \right| \leqslant \left| a _ {m} - a \right| + \left| a - a _ {n} \right| <   \varepsilon ,
$$

即 $\{a_{n}\}$ 是柯西数列.

反之, 假设 $\{a_{n}\}$ 是柯西数列. 我们先证明数列 $\{a_{n}\}$ 是有界的. 对于 $\varepsilon = 1$, 由柯西数列的定义, 存在正整数 $N$, 当 $m \geqslant N$ 时, $|a_{m} - a_{N}| < 1$, 有 $|a_{m}| < 1 + |a_{N}|$. 取

$$
M = \max \left\{\left| a _ {1} \right|, \left| a _ {2} \right|, \dots , \left| a _ {N - 1} \right|, 1 + \left| a _ {N} \right| \right\},
$$

则对于任意正整数 $n, |a_{n}| \leqslant M$，即 $\{a_{n}\}$ 有界.

由定理 1.3.3, $\{a_{n}\}$ 存在收敛的子列 $\{a_{n_k}\}$, 记 $a$ 为 $\{a_{n_k}\}$ 的极限. 我们证明 $a$ 是数列 $\{a_{n}\}$ 的极限. 对于任意 $\varepsilon > 0$, 由于 $\{a_{n}\}$ 是柯西数列, 故存在正整数 $N_{1}$, 当 $m, n \geqslant N_{1}$ 时,

$$
\left| a _ {m} - a _ {n} \right| <   \frac {1}{2} \varepsilon .
$$

> **注：** ① 波尔查诺 (Bolzano, 1781—1848), 捷克数学家. 他 1796 年入布拉格大学哲学院攻读哲学、物理学和数学, 1800 年又入神学院, 1805 年任该校宗教哲学教授, 1815 年成为波希米亚皇家学会的会员, 1818 年任该校哲学院院长. 波尔查诺的主要数学成就涉及分析学的基础问题, 对建立无穷集合理论也有重要见解.

> **注：** ② 魏尔斯特拉斯 (Weierstrass, 1815—1897), 德国数学家, 被誉为 “现代分析之父”. 他建立了函数极限的严格定义, 这是他对数学的一个贡献. 他是数学分析算术化的完成者, 是解析函数论的奠基人, 同时是一位卓越的大学数学教师.

§1.3 柯西准则

因为 $\lim_{n\to \infty}a_{n\varepsilon} = a,$ 对于上述 $\varepsilon >0$ ，存在正整数 $N_{2}$ ，当 $k\geqslant N_2$ 时，

$$
\left| a _ {n _ {k}} - a \right| <   \frac {1}{2} \varepsilon .
$$

取 $N = \max \{N_{1}, N_{2}\}$, 当 $n \geqslant N$ 时, 取 $k \geqslant N$, 则 $n_{k} \geqslant k \geqslant N$, 且同时有不等式

$$
\left| a _ {\bar {n}} - a _ {n _ {k}} \right| <   \frac {1}{2} \varepsilon , \quad \left| a _ {n _ {k}} - a \right| <   \frac {1}{2} \varepsilon .
$$

因此, $|a_{n}-a|\leqslant|a_{n}-a_{n_{k}}|+|a_{n_{k}}-a|<\varepsilon$ .所以

$$
\lim _ {n \to \infty} a _ {n} = a.
$$

柯西准则表明: 如果 $m$ 和 $n$ 充分大时, $a_m$ 和 $a_n$ 的距离可以任意小, 那么 $\{a_n\}$ 收敛. 它的优点是不需要知道 $\{a_n\}$ 的极限, 只要根据 $\{a_n\}$ 自身的特征就可以判断其收敛性.

#### 例 1.3.6 对于 $\theta \in \mathbb{R}$, 设 $a_{n} = \frac{\sin\theta}{2} + \frac{\sin\theta^{2}}{2^{2}} + \cdots + \frac{\sin\theta^{n}}{2^{n}}$, 证明 $\{a_{n}\}$ 收敛.

证明:对任意 $m, n \in \mathbb{N}_{+}, m \geqslant n,$ 有

$$
\begin{array}{r l} | a _ {m} - a _ {n} | & = \left| \frac {\sin \theta^ {n + 1}}{2 ^ {n + 1}} + \dots + \frac {\sin \theta^ {m - 1}}{2 ^ {m - 1}} + \frac {\sin \theta^ {m}}{2 ^ {m}} \right| \\ & \leqslant \frac {1}{2 ^ {n + 1}} \left(1 + \frac {1}{2} + \dots + \frac {1}{2 ^ {m - n - 1}}\right) \\ & = \frac {1}{2 ^ {n + 1}} \left(2 - \frac {1}{2 ^ {m - n - 1}}\right) <   \frac {1}{2 ^ {n}}. \end{array}
$$

对任意给定的 $\varepsilon > 0$, 必可取到正整数 $N$, 满足 $2^{N} > \frac{1}{\varepsilon}$, 所以对于任意的 $m, n \geqslant N$, 有

$$
\left| a _ {m} - a _ {n} \right| <   \frac {1}{2 ^ {n}} <   \frac {1}{2 ^ {N}} <   \varepsilon
$$

成立. 这说明 $\{a_{n}\}$ 是柯西数列, 因此 $\{a_{n}\}$ 收敛.

#### 例 1.3.7 证明数列  $\left\{1+\frac{1}{2}+\cdots+\frac{1}{n}\right\}$  发散.

证明:设  $a_{n}=1+\frac{1}{2}+\cdots+\frac{1}{n}$ ，则对任意  $n\in N_{+}$ ，取 m=2n，有

$$
\begin{array}{r l} & {\left| a _ {m} - a _ {n} \right| = \frac {1}{n + 1} + \frac {1}{n + 2} + \dots + \frac {1}{n + n}} \\ & {\qquad \geqslant \frac {1}{n + n} + \frac {1}{n + n} + \dots + \frac {1}{n + n} = \frac {1}{2}.} \end{array}
$$

所以对 $\varepsilon = \frac{1}{2}$, 不存在整数 $N$, 使得对于所有 $m, n \geqslant N$, 有 $|a_m - a_n| < \frac{1}{2}$. 因此数列 $\{a_n\}$ 不是柯西数列, 故数列 $\{a_n\}$ 发散.

46

数列的极限

# 第1章习题

习题1.1

1. 若对于无穷多个正数 $\varepsilon$, 存在正整数 $N$, 使得当 $n \geqslant N$ 时, $|a_n - a| < \varepsilon$, 能否断定 $\{a_n\}$ 以 $a$ 为极限? 为什么?

2. 若对于任意的正数 $\varepsilon > 0$, 存在正整数 $N$, 使得有无穷多个 $n > N$, $|a_{n} - a| < \varepsilon$, 能否断定 $\{a_{n}\}$ 以 $a$ 为极限? 为什么?

3. 若对于任意的正整数 $k$, 存在正整数 $N$, 使得当 $n \geqslant N$ 时, $|a_n - a| < \frac{1}{k}$, 能否断定 $\{a_n\}$ 以 $a$ 为极限, 为什么?

4. 用 $\varepsilon - N$ 语言完整地叙述: $\{a_{n}\}$ 不以 $a$ 为极限.

5. 设 $\{a_{n}\}$ 为一个数列, 证明: $a_{n} \to a$ 的充要条件是 $a_{n} - a \to 0$.

6. 用定义证明下列极限:

(1) $\lim_{n\to \infty}\frac{n + 1}{n} = 1;$ (2) $\lim_{n\to \infty}\frac{\sin n}{n} = 0;$ (3) $\lim_{n\to \infty}\frac{(-1)^n}{\sqrt{n + 1}} = 0;$ (4) $\lim_{n\to \infty}\frac{n}{5 + 3n} = \frac{1}{3};$

(5) $\lim_{n\to \infty}0.\underbrace{99\cdots 9}_{n\text{个}} = 1;$

(6) $\lim_{n\to \infty}r_n = 1$ ，其中 $r_n = \left\{ \begin{array}{ll}\frac{n - 1}{n}, & n\text{为偶数，}\\ \frac{n + 1}{n}, & n\text{为奇数}. \end{array} \right.$

7. 设数列 $\{x_{n}\}, \{y_{n}\}$ 收敛, $\lim_{n\to \infty}x_n = a, \lim_{n\to \infty}y_n = b,$ 且 $a > b$, 证明: 存在正整数 $N$, 当 $n \geqslant N$ 时, $x_{n} > y_{n}$.

8. 若 $a_{n} > b_{n}, n = 1,2,\dots$ ，且 $\lim_{n\to \infty}a_n = a,\lim_{n\to \infty}b_n = b,$ 证明: $a\geqslant b.$

9. 证明: 若 $a_{n} \to a (n \to \infty)$, 则对任一自然数 $k, a_{n+k} \to a (n \to \infty)$.

10. 证明: 若 $a_{n} \to a$, 则 $|a_{n}| \to |a|$. 反之是否成立?

11. 设数列 $\{x_{n}\}$ 收敛于 0, 而数列 $\{y_{n}\}$ 有界, 证明: $\lim_{n\to \infty}x_ny_n = 0$. 当 $\{y_{n}\}$ 无界时, 情况如何? 举出合适的例子说明.

12. 若 $\{a_n^3\}$ 收敛, 问 $\{a_n\}$ 是否收敛? 并说明理由.

13. 设 $\{a_{n}\}$ 为非负数列, 且 $a_{n} \to a > 0$, 证明: $\sqrt{a_{n}} \to \sqrt{a}$.

14. 若  $a_{2n-1} \geqslant b_{2n-1}, a_{2n} \leqslant b_{2n}, n = 1, 2, \cdots$ ，且  $\lim_{n \to \infty} a_n = a, \lim_{n \to \infty} b_n = b$ ，证明:a = b.

15. 利用夹逼定理计算下列极限:
(1)  $\lim_{n\to\infty}\sqrt[n]{n+a}, a>0;$

(2)  $\lim_{n\to\infty}\sqrt[n]{1+2+\cdots+n};$

第1章习题

![第1章图像：PDF 第 52 页，图像块 1](图片/第1章-P052-B01.png)

(3) $\lim_{n\to \infty}\left[\frac{1}{n^2} +\frac{1}{(n + 1)^2} +\dots +\frac{1}{(2n)^2}\right];$ (4) $\lim_{n\to \infty}\sqrt[n]{1^n + 2^n + \cdots + 9^n};$

(5) $\lim_{n\to \infty}\frac{n!}{n^n};$ (6) $\lim_{n\to \infty}\frac{1\cdot 3\cdot 5\cdot\cdots\cdot(2n - 1)}{2\cdot 4\cdot 6\cdot\cdots\cdot(2n)}.$

16. 求极限 $\lim_{n\to \infty}\left(1 + \frac{1}{n^2}\right)\left(1 + \frac{2}{n^2}\right)\dots \left(1 + \frac{n}{n^2}\right)$.

17. 利用极限运算法则计算下面数列的极限:

(1) $\lim_{n\to \infty}\frac{1000n}{n^2 + 1};$ (2) $\lim_{n\to \infty}\frac{3n^3 + 2n^2 - n + 1}{2n^3 + 3n^2 + 2};$

(3) $\lim_{n\to \infty}\frac{\sqrt[3]{n^2}\sin n!}{n + 1};$

(4) $\lim_{n\to \infty}\frac{\left(\sqrt{n^2 + 1} + n\right)^2}{\sqrt[3]{n^6 + 1}};$

(5) $\lim_{n\to \infty}\frac{(-2)^n + 3^n}{(-2)^{n + 1} + 3^{n + 1}};$

(6) $\lim_{n\to \infty}\left(\sqrt{n + 1} -\sqrt{n}\right);$

(7) $\lim_{n\to \infty}\left[\sqrt{(n + a)(n + b)} - n\right], a, b \in \mathbb{R};$ (8) $\lim_{n\to \infty}n\left(1 - \sqrt[5]{1 - \frac{1}{n}}\right);$

(9) $\lim_{n\to \infty}\left(\frac{1 + 2 + \cdots + n}{n + 2} -\frac{n}{2}\right);$

(10) $\lim_{n\to \infty}\left[\frac{1}{1\cdot 2} +\frac{1}{2\cdot 3} +\dots +\frac{1}{(n - 1)n}\right].$

18. (1) 设 $\{x_{n}\}, \{y_{n}\}$ 发散, $\{x_{n} + y_{n}\}$ 是否发散? 为什么?

(2) 设 $\{x_{n}\}, \{y_{n}\}$ 发散, $\{x_{n}y_{n}\}$ 是否发散? 为什么?

(3) 设 $\{x_{n}\}$ 收敛, $\{y_{n}\}$ 发散, $\{x_{n} + y_{n}\}$ 是否发散? 为什么?

19. 设 $\lim_{n\to \infty}x_ny_n = 0$ ，能否推出 $\lim_{n\to \infty}x_n = 0$ 或 $\lim_{n\to \infty}y_n = 0?$ 为什么？

20. 设数列  $\{a_{n}\}$  满足  $a_{n} \neq 0, n = 1, 2, \cdots$ ，且  $\lim_{n \to \infty} a_{n} = a$ ，是否有
$\lim_{n\to\infty}a_{n+1}=a?$  能否据此推断  $\lim_{n\to\infty}\frac{a_{n}}{a_{n+1}}=1?$

21. 研究极限  $\lim_{n\to\infty}\frac{a_{0}+a_{1}n+\cdots+a_{p}n^{p}}{b_{0}+b_{1}n+\cdots+b_{q}n^{q}}$  的收敛性, 其中 p,q 为正整数,  $a_{p}\neq0, b_{q}\neq0.$

习题1.2

22. 证明下列数列收敛, 并求其极限:

(1) $a_1 = \sqrt{2}, a_n = \sqrt{2a_{n-1}} (n = 2, 3, \cdots)$;

(2) $a_1 = \sqrt{c}, a_n = \sqrt{c + a_{n-1}}$, 其中 $c$ 是正常数;

(3) $a > 0$, $a_{1} = \frac{1}{2}\left(a + \frac{1}{a}\right)$, $a_{n+1} = \frac{1}{2}\left(a_{n} + \frac{2}{a_{n}}\right)$ ($n = 1, 2, \dots$).

23. 设 $0 < x_0 < \frac{\pi}{2}$, 作迭代序列 $x_n = \sin x_{n-1}, n = 1, 2, \cdots$, 证明:

48

第1章

$\lim_{n\to \infty}x_n = 0.$

24. 证明下列数列 $\{a_{n}\}$ 收敛:

(1) $a_{n} = \left(1 - \frac{1}{2}\right)\left(1 - \frac{1}{2^{2}}\right)\dots \left(1 - \frac{1}{2^{n}}\right);$

(2) $a_{n} = \frac{1}{3 + 1} +\frac{1}{3^{2} + 1} +\dots +\frac{1}{3^{n} + 1};$

(3) $a_{n} = \frac{10}{1} \cdot \frac{11}{3} \cdot \dots \cdot \frac{n + 9}{2n - 1}$;

(4) $a_{n} = \frac{n^{k}}{c^{n}}$ (其中 $c > 1, k$ 为正整数).

25. 设 $a_{n} = \frac{1}{n^{2}} + \frac{1}{n^{2} + 1} + \cdots + \frac{1}{n^{2} + 2n}$, 证明 $\{a_{n}\}$ 单调减少.

26. 设 $\{a_{n}\}$ 单调增加, $\{b_{n}\}$ 单调减少, 且 $\lim_{n\to \infty}(a_n - b_n) = 0$, 证明 $\{a_{n}\}$ 和 $\{b_{n}\}$ 收敛且极限相等.

27. (1) 证明数列 $a_{n} = \left(1 + \frac{1}{n}\right)^{n + 1}$ 严格单调减少有下界, 并求 $\lim_{n\to \infty}a_n$;

(2) 证明不等式 $\left(1 + \frac{1}{n}\right)^n < \mathrm{e} < \left(1 + \frac{1}{n}\right)^{n+1} (n = 1, 2, \cdots)$;

(3) 证明不等式 $\frac{1}{n + 1} < \ln \left(1 + \frac{1}{n}\right) < \frac{1}{n} (n = 1,2\dots)$;

(4) 利用夹逼定理证明  $\lim_{n\to\infty}\left(\frac{1}{n}+\frac{1}{n+1}+\cdots+\frac{1}{2n}\right)=\ln2;$

(5) 利用单调收敛准则证明下面极限存在:

$$
\lim _ {n \to \infty} \left(1 + \frac {1}{2} + \frac {1}{3} + \dots + \frac {1}{n} - \ln n\right).
$$

28. 设数列  $\{u_{n}\}$  由下式定义:  $u_{1}=2, u_{n+1}=\frac{u_{n}(u_{n}^{2}+3)}{3u_{n}^{2}+1}(n=1,2,\cdots)$ .
证明数列  $\{u_{n}\}$  收敛, 并求其极限.

29. 求下列极限:

(1) $\lim_{n\to \infty}\left(1 + \frac{1}{n}\right)^{2n - 1}$;

(2) $\lim_{n\to \infty}\left(1 - \frac{1}{n}\right)^n;$

(3) $\lim_{n\to \infty}\left(1 + \frac{1}{2n}\right)^{6n}$;

(4) $\lim_{n\to \infty}\left(1 - \frac{1}{n^2}\right)^n;$

(5) $\lim_{n\to \infty}\left(1 - \frac{1}{n - 2}\right)^{n + 1}$;

(6) $\lim_{n\to \infty}\left(\frac{n + 1}{n + 2}\right)^n;$

(7) $\lim_{n\to \infty}na^n$ ( $a$ 为常数, 且 $|a| < 1$); (8) $\lim_{n\to \infty}\frac{n^3}{a^n}$ ($a > 1$ 为常数).

第1章习题

习题1.3

30. 证明数列 $\{2 + (-1)^n\}$ 是发散的.

31. 找出数列  $\left\{n^{(-1)^{n}}\right\}$  的一个收敛的子列.

32. 设 $\{a_{n}\}$ 是单调增加数列, 证明: 如果存在 $\{a_{n}\}$ 的一个子列 $\{a_{n_{k}}\}$ 收敛于 $a$, 那么 $\{a_{n}\}$ 也收敛于 $a$.

33. 证明数列  $\left\{\frac{1}{1^{\alpha}}+\frac{1}{2^{\alpha}}+\frac{1}{3^{\alpha}}+\cdots+\frac{1}{n^{\alpha}}\right\}$  ( $\alpha>1$ ) 收敛.

34. 用 $\varepsilon - N$ 语言完整地叙述: 数列 $\{a_n\}$ 不是柯西数列.

35. 利用柯西准则讨论下列数列 $\{S_n\}$ 的收敛性:

(1) $S_{n} = a_{0} + a_{1}q + a_{2}q^{2} + \dots +a_{n}q^{n},|q| <   1,|a_{n}|\leqslant M$ (常数);

(2) $S_{n} = 1 + \frac{\sin 1}{2} + \frac{\sin 2}{2^{2}} + \cdots + \frac{\sin n}{2^{n}};$

(3) $S_{n} = \frac{\cos 1!}{1 \cdot 2} + \frac{\cos 2!}{2 \cdot 3} + \dots + \frac{\cos n!}{n(n + 1)}$;

(4) $S_{n} = 1 + \frac{1}{2^{2}} +\frac{1}{3^{2}} +\dots +\frac{1}{n^{2}}.$

36. 证明: 数列 $\{a_{n}\}$ 收敛的充要条件是: 对任意正整数 $k$, 存在 $N$, 当 $n \geqslant N$ 时, 对任意 $m$ 有 $|a_{n} - a_{n+m}| < \frac{1}{k}$.

37. 证明:如果有界数列 $\{a_{n}\}$ 不收敛，那么必存在两个子列 $\{a_{n_k}^{(1)}\}$ 与 $\{a_{n_k}^{(2)}\}$，使 $a_{n_k}^{(1)} \to A_1, a_{n_k}^{(2)} \to A_2$，而 $A_1 \neq A_2$.

38. 设数列 $\{a_{n}\}$ 满足: 对任意 $n \geqslant 1$, 有 $|a_{n+2} - a_{n+1}| \leqslant \frac{1}{2} |a_{n+1} - a_{n}|$, 证明 $\{a_{n}\}$ 收敛.

39. 证明: 对数列 $\{a_{n}\}$, 若存在常数 $c > 0$, 使对任何 $n$, 有

$$
| a _ {2} - a _ {1} | + | a _ {3} - a _ {2} | + \dots + | a _ {n + 1} - a _ {n} | \leqslant c,
$$

则 $\{a_{n}\}$ 收敛.

40. 证明数列 $\{\sin n\}$ 发散.

41. 设数列 $\{a_{n}\}$ 满足条件 $|a_{n + 1} - a_n| \leqslant cq^n$ ($c > 0, 0 < q < 1$), 证明 $\{a_{n}\}$ 收敛.

![第1章图像：PDF 第 55 页，图像块 20](图片/第1章-P055-B20.png)

第1章重难点讲解

![第1章图像：PDF 第 55 页，图像块 22](图片/第1章-P055-B22.png)

第1章部分习题参考答案与提示
