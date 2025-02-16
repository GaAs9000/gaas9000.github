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


{{< spoiler text="👉 Why we need to check the difference between the roots" >}}

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
{{< /spoiler >}}

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

\[
a_n(r) \;=\; -\,\frac{1}{F\bigl(r+n\bigr)} \;\sum_{k=0}^{n-1} \Bigl[\bigl(r+k\bigr)\,p_{n-k} \;+\; q_{n-k}\Bigr]\,a_k(r),
\quad
a_0(r) \;=\; 1,
\]
where
\[
F(r) \;=\; \bigl(r - \tfrac{3}{2}\bigr)\,\bigl(r + 2\bigr),
\]
and all \(p_i,\,q_i=0\) except \(p_0 = p_1 = \tfrac{3}{2}\) and \(q_0 = -3.\)

• **Step 1: Substitute \(F(r+n)\).**  
Replace \(F(r+n)\) with \(\bigl(r + n - \tfrac{3}{2}\bigr)\,\bigl(r + n + 2\bigr).\)

• **Step 2: Handle the Summation.**  
For \(n=1\):
\[
a_1(r)
=\;
-\,\frac{1}{\bigl(r+1 - \tfrac{3}{2}\bigr)\,\bigl(r+1+2\bigr)}
\;\bigl[\,(r)\,p_1 + q_1\bigr]\,a_0(r).
\]
Given \(p_1=\tfrac{3}{2}\) and \(q_1=0\), we get
\[
a_1(r)
=\;
-\,\frac{\tfrac{3}{2}\,r}{\bigl(r - \tfrac{1}{2}\bigr)\,\bigl(r+3\bigr)}.
\]

For \(n\ge2\), the only nonzero terms in the sum occur when \(n-k=1\). Hence,
\[
a_n(r)
=\;
-\,\frac{(r + n - 1)\,\tfrac{3}{2}}{\bigl(r+n - \tfrac{3}{2}\bigr)\,\bigl(r+n+2\bigr)}
\,a_{n-1}(r).
\]

• **Step 3: Iterate (and find a pattern).**  
By applying the recurrence repeatedly, we see a pattern emerge for \(a_n(r)\).  

• **Step 4: Generalize.**  
A typical closed form (for \(n\ge4\)) looks like
\[
a_n(r)
=\;
(-1)^n\,3^n
\,\frac{r\,(r+1)\cdots(r+n-1)}{\bigl(2r-1\bigr)\,\bigl(2r+1\bigr)\cdots\bigl(2r+2n-3\bigr)\,\bigl(r+3\bigr)\,\bigl(r+4\bigr)\cdots\bigl(r+n+2\bigr)}.
\]

### Summary

1. **Two Independent Solutions**  
    Substitute \(r_1=\tfrac{3}{2}\) and \(r_2=-2\) into the recurrence to get two sets of coefficients \(\{a_n(r_1)\}\) and \(\{a_n(r_2)\}\). These form two linearly independent series solutions, \(y_1(x)\) and \(y_2(x)\).

2. **General Solution**  
    Since this is a second-order linear ODE, the full solution on \((0,\infty)\) is
    \[
    y(x) \;=\; c_1\,y_1(x) \;+\; c_2\,y_2(x),
    \]
    where \(c_1\) and \(c_2\) are constants.

3. **Interval of Validity**  
    The coefficients \(p(x)\) and \(q(x)\) are analytic on \(\mathbb{C}\setminus\{0\}\). Because the radius of convergence is infinite and the only singularity is at \(x=0\), the series solution is valid for \(x>0\), i.e. \((0,\infty)\).

---

c) 

**Methodology Summary**

1. **Identify Equation Type and Singularities:**  
First, identify the type of the given differential equation (e.g., second-order linear with constant/variable coefficients). The key is to identify the **singular points** of the equation, especially **regular singular points**. Problem (a) explicitly states that $x = 0$ is a regular singular point.

2. **Solve Near the Singular Point (Usually Using the Frobenius Method):**  
For regular singular points, we typically use the **Frobenius method** (or generalized power series method) to find series solutions near the singular point. This usually involves:  
• Assuming a solution of the form $y(x) = x^r \sum_{n=0}^{\infty} a_n x^n$.  
• Substituting the assumed solution into the differential equation.  
• By comparing coefficients of like powers of $x$, obtaining the **indicial equation** (for $r$) and a recurrence relation for $a_n$.  
• Solving the indicial equation to get the roots $r_1, r_2$.  
• Based on the nature of the roots (real and distinct, real and equal, or complex), obtaining the corresponding **fundamental set of solutions** $y_1(x)$ and $y_2(x)$. Note that these solutions are usually solutions near the singular point (e.g., $x > 0$ or $x < 0$). Problem (b) is about solving for the solution on $(0, \infty)$.

3. **Consider the Domain and Extension of Solutions:**  
• **Local vs. Global Solutions:** The solutions obtained by the Frobenius method are usually local solutions near the singular point. We need to consider how to extend these solutions to a larger domain.  
• **Piecewise Domains:** For intervals containing the singular point, we might need to consider the solution piecewise. For example, solving separately on $(0, \infty)$ and $(-\infty, 0)$. Problem (c) asks for the solutions on $(-\infty, 0)$ and on $\mathbb{R}$.  
• **Properties at the Singular Point:** At the singular point (e.g., $x = 0$), the properties of the solution might be special. The solution might not be differentiable everywhere, or even continuously differentiable. We need to analyze the continuity and differentiability of the solution at the singular point to determine if the solution can be extended to a larger interval containing the singular point.

4. **Analyze Uniqueness and Linear Combinations of Solutions:**  
The general solution of a linear homogeneous differential equation is a linear combination of the fundamental set of solutions. On a specific interval, the form of the general solution is determined. We need to pay attention to the **uniqueness** of the solution and how to construct the general solution from the fundamental set.

5. **Pay Special Attention to the Influence of Singularities:**  
Singular points are crucial to the behavior of solutions to differential equations. At singular points, the properties of the solution might be different from those at other points. For example, the solution might exhibit singularities (unboundedness, non-differentiability, etc.). Understanding the influence of singularities on the solution is central to solving these types of problems.

**Problem (c): Using the result of (b), state the general solution of (DE) on $(-\infty, 0)$ and on $\mathbb{R}$.**

1. **General Solution on $(-\infty, 0)$:**  
• **Given Information:** The problem explicitly states that the solution on $(-\infty, 0)$ is $y(x) = c_1\,y_1^-(x) + c_2\,y_2^-(x)$, and $y_2^-(x)$ is the same function as $y_2(x)$ in (b).  
• **Understanding $y_1^-(x)$:** $$y_1^-(x) = (-x)^{3/2} \sum_{n=0}^{\infty} a_n x^n = |x|^{3/2} \sum_{n=0}^{\infty} a_n x^n.$$ 

The term $(-x)$ appears in the power function because we are considering the case $x < 0$, to ensure that the value under the square root is positive. $|x|^{3/2}$ is also used to emphasize the case for $x < 0$.  
• **Summary of the General Solution on $(-\infty, 0)$:**  
Therefore, on $(-\infty, 0)$, the form of the general solution is similar to that on $(0, \infty)$, but the form of the fundamental set is slightly different, mainly in the form of $y_1^-(x)$. A common student mistake is to directly use $y_1(x)$ and $y_2(x)$ obtained in (b) as the solution on $(-\infty, 0)$, which is incorrect. Because $y_1(x)$ is defined for $x > 0$, applying it directly is inappropriate. The problem has clearly given the form of $y_1^-(x)$, and we should use it directly.

So, for $(-\infty, 0)$, the general solution is $y(x) = c_1\,y_1^-(x) + c_2\,y_2(x)$, where $y_1^-(x) = |x|^{3/2} \sum_{n=0}^{\infty} a_n x^n$ (the specific series form needs to be obtained by solving using the Frobenius method; the problem only gives the form here), and $y_2(x)$ is the second fundamental solution obtained in (b).

2. **General Solution on $\mathbb{R}$:**  
• **Given Information:** The problem explicitly states that many students incorrectly claim that the solution on $\mathbb{R}$ is a piecewise function:
```md
$$
x \mapsto
\begin{cases}
y_1(x), & x > 0,\\
0, & x = 0,\\
y_1^{-}(x), & x < 0
\end{cases}
$$
```
and points out that this solution is **incorrect**.  
• **Analysis of the Error:** The key explanation in the problem is: “Since $y_1(x) \approx x^{3/2}$ for $x \downarrow 0$, the (unique) continuous extension of $y_1(x)$ to $[0,\infty)$ (obtained by setting $y_1(0) = 0$) is **not** twice differentiable at $x = 0$ (only once differentiable).”  
  - **Continuity:** For the solution to be meaningful on $\mathbb{R}$, we need to ensure that the solution is continuous at $x = 0$. If $\lim_{x\to 0^+} y_1(x) = 0$ and $\lim_{x\to 0^-} y_1^-(x) = 0$, and we define $y(0) = 0$, then this piecewise function is continuous at $x = 0$. The problem mentions $y_1(0) = 0$ to ensure continuity.  
  - **Differentiability:** The differential equation is second-order, so the solution must be **twice differentiable** on $\mathbb{R}$. The problem points out that $y_1(x)$ (and $y_1^-(x)$) is **not** twice differentiable at $x = 0$, only once differentiable. This is because $y_1(x) \approx x^{3/2}$, and its second derivative will approach infinity (or not exist) near $x = 0$.  
  - **Requirements for Solutions of Differential Equations:** The solution of a differential equation must satisfy the differential equation itself. If a function is not twice differentiable, it cannot be a solution of a second-order differential equation (at the points where the second derivative does not exist).

• **Correct Conclusion:**  
Since neither $y_1(x)$ nor $y_2(x)$ (and neither $y_1^-(x)$ nor $y_2^-(x)$) can maintain twice differentiability at $x = 0$ (unless it is the trivial solution $y(x) \equiv 0$), therefore, the only possible solution on the entire real line $\mathbb{R}$ is the trivial solution $y(x) \equiv 0$. The last sentence in the problem, “hence the only solution on $[0,\infty)$, and hence on $\mathbb{R}$, is $y(x) \equiv 0$,” confirms this conclusion.

**Summary of the Answer to (c):**  
• **General Solution on $(-\infty, 0)$:** $y(x) = c_1\,y_1^-(x) + c_2\,y_2(x)$, where $y_1^-(x) = |x|^{3/2} \sum_{n=0}^{\infty} a_n x^n$, and $y_2(x)$ is the second fundamental solution obtained in (b).  
• **General Solution on $\mathbb{R}$:** $y(x) \equiv 0$ (the zero solution). This is because non-trivial solutions cannot maintain twice differentiability at $x = 0$, and thus do not satisfy the requirement for solutions of the differential equation on $\mathbb{R}$.

### Q3 