# $\varepsilon -N$语言

Created: February 25, 2023 4:38 PM
State: stable

$a_n任意接近A，用数学语言描述：$

> $\forall \varepsilon > 0 (无论多小),    |a_n - A| < \varepsilon$
>

$上述接近是有条件的：n \to \infty 时 (n 足够大时)$

> $\exists N (足够大), 当 n \geq N 时$
>

---

$\lim_{x \to x_0} f(x) = A \quad \Leftrightarrow \quad 对~ \forall \varepsilon >0, \, \exists \delta > 0 ~使得当 ~0<|x-x_0| < \delta~时，有~ |f(x) - A| < \varepsilon$

// 总是存在一个 $\delta$ 使 $0<|x-x_0| < \delta$ 满足 且有 $|f(x) - A| < \varepsilon$  //如果不满足则极限结果是假的

// $|f(x) - A|$ 这个要满足无限小,因为 任意大于0的 $\varepsilon$ (其实就是在强调 $\varepsilon$ 无限小)

// 也就是说 需要找到一个 $\delta$ 去满足 $0<|x-x_0| < \delta$ 的前提下, 且 $x$ 的取值范围总是满足 $|f(x) - A| < \varepsilon$  //一般 $\delta$ 的值都是与 $\varepsilon$ 相互联系的,比如: $\delta = \frac{1}{\varepsilon}$

---

# 参考

[【高等数学】用ε-δ语言证明函数极限](https://zhuanlan.zhihu.com/p/84880461)
