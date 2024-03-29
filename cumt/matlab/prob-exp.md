# 概率论实验 - 代码和运行结果

<strong>实验时间：</strong>2023 年秋季

## 代码

不想下载 MATLAB 的同学可以使用教育邮箱登录 [MATLAB Online](https://matlab.mathworks.com) 在线使用 MATLAB.

#### 初始化

先指定 $m$ 值，以 $m=4$  为例：

```matlab
clear;
m = 4;
```

**Note:** 事先声明 $m$ 的值然后依次运行下面的代码即可，在下面的代码前添加上面的内容也是等价的。

#### 第一题

在一级品率为 $0.3$ 的灯泡中，随机地抽取 $10+m$ 个，求其中有 $m+1$ 个一级品的概率

```matlab

p = 0.3;
n = 10 + m;
prob1 = nchoosek(n, m + 1) * p^(m + 1) * (1 - p)^(n - (m + 1));

prob1
```

#### 第二题

已知随机变量 $\xi$ 服从正态分布，$\xi \sim N(2,m^2)$，求 $P(\xi \geq m)$。

```matlab
mu = 2;
sigma = m;
ltm = normcdf(m, mu, sigma);
prob2 = 1 - ltm;

prob2
```

#### 第三题

计算期望 $E(X)$ 和方差 $D(X)$。$X$ 的分布律为：

| $X_i$ | $m$   | $m+1$ | $m+2$ | $m+3$ |
|:-----:|:-----:|:-----:|:-----:|:-----:|
| $P_k$ | $0.3$ | $0.2$ | $0.3$ | $0.2$ |

```matlab
X = [m, m + 1, m + 2, m + 3];
P = [0.3, 0.2, 0.3, 0.2];
EX3 = sum(X .* P);
DX3 = sum((X - EX3).^2 .* P);

EX3, DX3
```

#### 第四题

已知连续型随机变量 $X$ 的概率密度函数为：

$$
f(x) =
\begin{cases}
\frac{3x^2}{m^3}, & 0 < x < m \\
0, & \text{others}
\end{cases}
$$

求 $X$ 的数学期望和方差。

```matlab
pdf = @(x) 3.*x.^2 ./ m^3;
EX4 = integral(@(x) x.*pdf(x), 0, m);
DX4 = integral(@(x) (x - EX4).^2.*pdf(x), 0, m);

EX4, DX4
```

## 运行结果举要

| $\boldsymbol{m}$ | prob1    | prob2    | EX3       | DX3      | EX4      | DX4      |
|:----------------:|:--------:|:--------:|:---------:|:--------:|:--------:|:--------:|
| **1**            | $0.1998$ | $0.8413$ | $2.4000$  | $1.2400$ | $0.7500$ | $0.0375$ |
| **2**            | $0.2397$ | $0.5000$ | $3.4000$  | $1.2400$ | $1.5000$ | $0.1500$ |
| **3**            | $0.2337$ | $0.3694$ | $4.4000$  | $1.2400$ | $2.2500$ | $0.3375$ |
| **4**            | $0.1963$ | $0.3085$ | $5.4000$  | $1.2400$ | $3$      | $0.6000$ |
| **5**            | $0.1472$ | $0.2743$ | $6.4000$  | $1.2400$ | $3.7500$ | $0.9375$ |
| **6**            | $0.1010$ | $0.2525$ | $7.4000$  | $1.2400$ | $4.5000$ | $1.3500$ |
| **7**            | $0.0644$ | $0.2375$ | $8.4000$  | $1.2400$ | $5.2500$ | $1.8375$ |
| **8**            | $0.0386$ | $0.2266$ | $9.4000$  | $1.2400$ | $6$      | $2.4000$ |
| **9**            | $0.0220$ | $0.2184$ | $10.4000$ | $1.2400$ | $6.7500$ | $3.0375$ |
| **10**           | $0.0120$ | $0.2119$ | $11.4000$ | $1.2400$ | $7.5000$ | $3.7500$ |

其中：

- `prob1` 为第一题的输出
- `prob2` 为第二题的输出
- `EX3` 和 `DX3` 为第三题的输出
- `EX4` 和 `DX4` 为第四题的输出。

## 输出案例

以 $m=4$ 为例，输出如下：

#### 第一题

```matlab
prob1 =

    0.1963
```

#### 第二题

```matlab
prob2 =

    0.3085
```

#### 第三题

```matlab
EX3 =

    5.4000


DX3 =

    1.2400
```

#### 第四题

```matlab
EX4 =

    3


DX4 =

    0.3375
```

## Credits

Published by [Cnily03](https://github.com/Cnily03) on Nov, 24th, 2023.

**Email:** [contact@cnily.me](mailto:contact@cnily.me)
