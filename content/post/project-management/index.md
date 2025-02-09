---
title: ✅ Math285 Final Review
summary: This is the review note for Math285 Final (Spring 2025) by Jiashen Ren.
date: 2025-02-07
authors:
  - admin
tags:
  - Math285
image:
  caption: 'Math285 Class'
---

## Q2:Frobenius method

### Sample Problem

Consider the differential equation

$$2x^2y'' + 3x(x+1)y' - 6y = 0. \qquad \text{(DE)}$$

a) Verify that $x_0 = 0$ is a regular singular point of (DE).

b) Determine the general solution of (DE) on $(0, \infty)$.

c) Using the result of b), state the general solution of (DE) on $(-\infty, 0)$ and on $\mathbb{R}$.

### Background Knowledge

1. **singular point and regular singular point** 

    * $$P(x)y'' + Q(x)y' + R(x)y = 0$$

      if $P(x_0) = 0$, $x_0$ is a singular point

    * $$y'' + p(x)y' + q(x)y = 0$$  
  
      $p(x) = \frac{Q(x)}{P(x)}$,  $q(x) = \frac{R(x)}{P(x)}$
      If $x_0$ is a singular point, and $(x-x_0)p(x)$ and $(x-x_0)^2q(x)$ are finite as $x \to x_0$, then $x_0$ is a regular singular point.

2. Frobenius method

    $$F(r) = r^2 + (P_0 - 1)r + q_0$$

    $P_0 = \lim_{x \to x_0} xp(x)$ and $q_0 = \lim_{x \to x_0} x^2q(x)$

    Solve for $r_1, r_2$

    $$y(x) = (x-x_0)^{r} \sum_{n=0}^{\infty} a_n (x-x_0)^n$$

    Substitute $y(x)$, $y'(x)$, $y''(x)$ into the ODE to solve for $a_n$

    You should obtain a relationship between $a_n$ and $a_{n+1}$ 
    Then solve the sequence

### Solution

a) 
The explicit form of (DE) is

$$y'' + \frac{3(x+1)}{2x}y' - \frac{3}{x^2}y = 0$$

$p(x) := \frac{3}{2} \frac{1}{x} + \frac{3}{2}$ has a pole of order 1 at 0, and $q(x) := -\frac{3}{x^2}$ has a pole of order 2 at 0.  This shows that 0 is a regular singular point of (DE).

b)
**1. Verification of Regular Singular Point and Calculation of Indicial Equation:**

*   **Explicit Form:** First, rewrite the original differential equation (DE) into the standard form:
    $$y'' + p(x)y' + q(x)y = 0$$

    to obtain $p(x)$ and $q(x)$.

*   **Order of Poles:** By observation, $p(x)$ has a pole of order 1 at $x=0$, and $q(x)$ has a pole of order 2 at $x=0$. This confirms that $x=0$ is a regular singular point.
*   **Indicial Equation:** Calculate $p_0$ and $q_0$:

    $$p_0 = \lim_{x \to 0} \left[ x \cdot p(x) \right] = \frac{3}{2}$$

    $$q_0 = \lim_{x \to 0} \left[ x^2 \cdot q(x) \right] = -3$$
    Then, construct the indicial equation:

    $$r^2 + (p_0 - 1)r + q_0 = 0$$

    $$r^2 + (1/2)r - 3 = 0$$

    Solve this quadratic equation to get the roots: $r_1 = 3/2$ and $r_2 = -2$.

**2. Constructing Series Solutions:**

*   **Two Linearly Independent Solutions:** Since the difference between the roots $r_1 - r_ 2 = 3/2 - (-2) = 7/2$ is not an integer, the Frobenius method guarantees two linearly independent series solutions, in the form:

    $$y_1(x) = x^{3/2} \sum_{n=0}^{\infty} a_n x^n = \sum_{n=0}^{\infty} a_n x^{n+3/2}$$ 

    $$y_2(x) = x^{-2} \sum_{n=0}^{\infty} b_n x^n = \sum_{n=0}^{\infty} b_n x^{n-2}$$

    where \(a_0 = b_0 = 1\) (normalization condition).

```markdown
{{</* spoiler text="👉 Why we need to check the difference between the roots" */>}}

这是 Frobenius 方法的一个核心结论。 让我解释一下为什么当指标根之差不是整数时，可以保证有两个线性无关的级数解：

**Frobenius 方法的基本思想**

Frobenius 方法假设解的形式为：

$$
y(x) = (x - x_0)^r \sum_{n=0}^{\infty} a_n (x - x_0)^n = \sum_{n=0}^{\infty} a_n (x - x_0)^{n+r}
$$

其中 \(x_0\) 是正则奇点，\(r\) 是待定的指标，\(a_n\) 是系数。 我们将这个级数代入微分方程，并通过比较系数得到关于 \(r\) 的指标方程（一个二次方程）和关于系数 \(a_n\) 的递推关系。

**指标方程和解的结构**

指标方程通常是 \(r\) 的二次方程，有两个根 \(r_1\) 和 \(r_2\) (假设 \(r_1 \geq r_2\))。 这两个根决定了解的 *基本形式*。

**关键：根的差的影响**

*   **情况 1：\(r_1 - r_2\) 不是整数**

    在这种情况下，我们可以直接得到两个线性无关的解：

    *   \(y_1(x) = (x - x_0)^{r_1} \sum_{n=0}^{\infty} a_n (x - x_0)^n\)  (使用 \(r_1\) 和递推关系)
    *   \(y_2(x) = (x - x_0)^{r_2} \sum_{n=0}^{\infty} b_n (x - x_0)^n\)  (使用 \(r_2\) 和递推关系)

    这两个解在 \(x=x_0\) 附近的 leading term （主导项）分别是 \((x-x_0)^{r_1}\) 和 \((x-x_0)^{r_2}\)。 因为 \(r_1\) 和 \(r_2\) 不同，且它们的差不是整数，这意味着这两个级数 *不可能* 通过乘以一个常数而互相转化。 也就是说，它们是线性无关的。 关键点是这个非整数差确保级数中的每一项都不会“抵消”或“重复”。

*   **情况 2：\(r_1 = r_2\) (重根)**

    只有一个指标根。直接用 Frobenius 方法只能找到一个解 \(y_1(x)\)。第二个线性无关的解需要包含对数项（logarithmic term）：

    $$
    y_2(x) = y_1(x) \ln(x - x_0) + (x - x_0)^{r_1} \sum_{n=0}^{\infty} b_n (x - x_0)^n
    $$
    求系数和 \(y_1(x)\) 的递推关系是不同的.

*   **情况 3：\(r_1 - r_2\) 是正整数**

    这是最复杂的情况。 我们尝试用较小的根 \(r_2\) 构造解 \(y_2(x)\) 时，可能会遇到递推关系“卡住”的情况（分母为零）。 这时，第二个解 \(y_2(x)\) 可能具有以下两种形式之一：

    *   **形式 1 (无对数项):**  \(y_2(x) = (x - x_0)^{r_2} \sum_{n=0}^{\infty} b_n (x - x_0)^n\) (虽然这种情况较少见，但确实可能发生，此时递推关系“幸运地”没有卡住)

    *   **形式 2 (有对数项):**
        $$
        y_2(x) = A y_1(x) \ln(x - x_0) + (x - x_0)^{r_2} \sum_{n=0}^{\infty} b_n (x - x_0)^n
        $$
        其中 \(A\) 是一个非零常数。这种情况更常见。

**直观理解（为什么非整数差很重要）**

想象一下两个级数：

*   \(y_1(x) = x^{3/2} (1 + a_1 x + a_2 x^2 + \ldots)\)
*   \(y_2(x) = x^{-2} (1 + b_1 x + b_2 x^2 + \ldots)\)

\(y_1(x)\) 中的各项的指数是 \(3/2, 5/2, 7/2, \ldots\)，而 \(y_2(x)\) 中的各项的指数是 \(-2, -1, 0, 1, 2, \ldots\)。 因为指数的 *差异* 永远不会是整数，所以你不可能通过调整 \(y_1(x)\) 的系数来得到 \(y_2(x)\) 中的任何一项。 这就是线性无关的本质。

如果差是整数，比如：

*    \(y_1(x) = x^2 (1 + a_1 x + \ldots)\)
*    \(y_2(x) = x^0 (1 + b_1 x + \ldots)\)

那么理论上，\(y_1\) 的级数部分和 \(y_2\) 的级数部分有可能通过不同的系数相等。 这时必须检查递推公式。如果递推公式无解（分母为 0），必须引入对数。

**总结**

当指标根之差不是整数时，Frobenius 方法直接给出的两个级数解，由于其首项（leading term）的指数不同且差不是整数，保证了它们是线性无关的。 这是 Frobenius 方法的一个漂亮且重要的结果，使得在正则奇点附近寻找级数解成为可能。
{{</* /spoiler */>}}
```
**3. Solving for the First Solution y1(x):**

*   **Substitute into Original Equation:** Substitute the series forms of \(y_1(x)\), \(y_1'(x)\), and \(y_1''(x)\) into the original differential equation.
*   **Combine Series:** Combine coefficients of like powers of \(x\).
*   **Recurrence Relation:** By setting the coefficients of each power of \(x\) to zero, obtain the recurrence relation for the coefficients \(a_n\):
    $$
    a_n = -\frac{3(2n + 1)}{2n(2n + 7)} a_{n-1}
    $$
*   **Calculate Coefficients:** Starting from \(a_0 = 1\), use the recurrence relation to calculate \(a_1, a_2, a_3, \ldots\).
*   **Write \(y_1(x)\):** Substitute the calculated coefficients into the series expression for \(y_1(x)\).

**4. Solving for the Second Solution \(y_2(x)\):**

*   **Repeat Steps:** Repeat the above process for \(y_2(x)\) (substitution, combination, recurrence).
*   **Recurrence Relation:** Obtain the recurrence relation for \(b_n\):
    $$
    b_n = \frac{3(n - 3)}{n(2n - 7)} b_{n-1}
    $$
*   **Calculate Coefficients:** Starting from \(b_0 = 1\), use the recurrence relation to calculate \(b_1, b_2, b_3, \ldots\). Note that \(b_3, b_4, \ldots\) are zero.
*   **Write \(y_2(x)\):** Substitute the calculated coefficients into the series expression for \(y_2(x)\).

**5. General Solution:**

Finally, the general solution of the differential equation is the linear combination of \(y_1(x)\) and \(y_2(x)\):

$$
y(x) = C_1 y_1(x) + C_2 y_2(x)
$$

where \(C_1\) and \(C_2\) are arbitrary constants.

---
**Alternative solution:**

---
