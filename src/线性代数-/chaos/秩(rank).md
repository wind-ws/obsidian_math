
依赖: [[src/线性代数-/chaos/k阶子式|k阶子式]]


> [!dy定义] 
> 矩阵$A$的秩（记为$rank~~A$）是$A$的[[src/线性代数-/向量/子空间/四个基本子空间/列空间|列空间]]的[[src/线性代数-/向量/子空间/子空间的维数(dim)|维数]].

通常表示为  ${\displaystyle \mathrm {r} (A)}$ ， ${\displaystyle \mathrm {rank} (A)}$ 或 ${\displaystyle \mathrm {rk} (A)}$ 

设 ${\displaystyle A}$ 为 ${\displaystyle m\times n}$ 矩阵。若 ${\displaystyle A}$ 至少有一个 ${\displaystyle r}$ 阶非零子式，而其所有 ${\displaystyle r+1}$ 阶子式全为零，即矩阵的最高阶非零子式的阶数为r。则称 ${\displaystyle r}$ 为 ${\displaystyle A}$ 的秩。



> [!dl定理] (秩定理)
> 如果一矩阵$A$有$n$列，则$rank~~A+dim~~Nul~~A=n$


### 结论
#### 初等变换不改变矩阵的秩
设$A$是$m\times n$矩阵, $P,Q$分别是$m$阶,$n$阶可逆矩阵,则
$$
r(A)=r(PA)=r(AQ)=r(PAQ)
$$
#### 三秩相等
$r(A)(矩阵的秩)=A的行秩=A的列秩$

#### 其他
设$A$是$m\times n$矩阵,$B$是满足有关矩阵运算要求的矩阵,则
1. $0\leq r(A)\leq \min \{m,n\}$
2. $r(kA)=r(A)~~(k\neq 0)$
3. $r(AB)\leq \min \{r(A),r(B)\}$
4. $r(AB)\geq r(A)+r(B)-n$ ($n$是列数)
5. $r(A+B)\leq r([A~~B])\leq r(A)+r(B)$
6. $\displaystyle{r(A^{*})=\begin{cases}n,&r(A)=n\\1,&r(A)=n-1\\0,&r(A)<n-1\end{cases}}$
7. $r(A)=n\Longleftrightarrow r(A^{*})=n$
8. $r(A)=n-1\Longleftrightarrow r(A^{*})=1$
9. $r(A)<n-1\Longleftrightarrow r(A^{*})=0$




