---
layout: page
title: §4. Неразложимые матрицы
---



<div style="border-left: 5px solid LimeGreen; padding: 10px 20px; margin: 20px 0">

<b>Определение 3.</b> Пусть \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\). Будем называть матрицу \(A\) <u>неразложимой</u>, если существует собственное подмножество \(J\) множества\(N = \{1, \dots, n\}\) (\(J \neq \emptyset, N\)), такое, что \(a_{ij} = 0\), если \(i \notin J\), \(j \in J\)

</div>

*Замечание.* Можно дать эквивалентное определение: существует матрица перестановок $$E_\pi$$ т.ч.

$$E_\pi^T AE_\pi = \begin{pmatrix}
A_{11} & A_{12} \\
O & A_{22}
\end{pmatrix},$$

где $$A_{11}$$ состоит из индексов $$j \in J$$, матрица $$A_{22}$$ — индексов $$i \notin J$$, обе матрицы квадратные.

Экономический смысл определения в том, что существует группа отраслей $$J$$, которая может существовать независимо от остальных, т.е. использовать только свою продукцию при производстве.


*Предложение 1.* Пусть $$A = \|a_{ij}\|_{i,j=1}^n \geq 0$$. Тогда матрица $$A$$ является разложимой $$\Leftrightarrow$$ является разложимой матрица $$A^T$$.



<div style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<b>Теорема (Критерий разложимости неотрицательной матрицы)</b>

Пусть \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\). Для того, чтобы матрица \(A\) была разложимой, необходимо и достаточно, чтобы 

$$\exists \hat{\vec x} \geq 0, \hat{\vec x} \neq 0, \hat{\vec x} \ngtr 0, \mu \geq 0:\ A\hat{\vec x} \leq \mu\hat{\vec x}$$

</div>

*Примечание.* Вектор $$\hat{\vec x} \geq 0, \hat{\vec x} \neq 0, \hat{\vec x} \ngtr 0$$ назовем *полуположительным*.

▶︎ $$\dots$$ ◼︎

<div style="border-left: 5px solid LimeGreen; padding: 10px 20px; margin: 20px 0">

<b>Определение 3'.</b> Пусть \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\). Будем говорить, что матрица \(A\) является <u>неразложимой</u>, если она не является разложимой или нулевой матрицей 1-го порядка.

</div>



<div style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<b>Теорема 4.</b> Пусть \(A = \|a_{ij}\|_{i,j=1}^n \geq 0\) неразложимая матрица. Тогда <br> <br>
<ol>
<li> Число Фробениуса-Перрона \(\lambda_A > 0\) и вектор Фробениуса-Перрона \(\vec x_A > 0\) (до этого определяли число и веткор так, чтобы \(A\vec x_A = \lambda(A)\vec x_A, \vec x_A \geq 0, \vec x_A \neq 0\)) </li> <br>


<li> Если \(A\vec y = \lambda_A \vec y\), \(\vec y \neq 0\), то \(\exists\mu:\ \vec y = \mu\vec x_A\) (т.е. геометрическая кратность \(\lambda_A\) равна \(1\)) </li>
</ol>
</div>



*Доказательство.* 

1. Допустим противное, что $$\vec x_A \ngtr 0$$. По критерию разложимости получается, что $$A$$ разложимая матрица. Противоречие $$\Rightarrow$$ $$\vec x_A > 0$$

$$A \neq 0 \Rightarrow A\vec x_A \neq 0 \Rightarrow \lambda_A \neq 0 \Rightarrow \lambda_A > 0$$


2. Без ограничения общности, считаем, что $$\vec y \in \mathbb R^n$$. Рассмотрим векторы $$\vec x(t) = \vec y - t\vec x_A$$. Хотим выбрать такое $$t$$, чтобы $$\vec x(t)$$ был неотрицательным. Возьмем

$$\min_{1\leq j\leq n} \frac{[\vec y]_j}{[\vec x_A]_j} = \theta$$

$$\Rightarrow [\vec y]_j \geq \theta [\vec x_A])j$$

$$[\vec x(\theta)]_j \geq 0, \quad j=1,\dots,n$$

$$\Rightarrow \vec x(\theta) \geq 0$$

На некоторых компонентах этот минимум достигается $$\Rightarrow$$ $$x(\theta) \ngtr 0$$.

$$A\vec x(\theta) = A\vec y - \theta A\vec x_A = \lambda_A \vec y - \theta\lambda_A\vec x_A = \lambda_A\vec x(\theta)$$

Если $$\vec x_A \neq 0$$, то по критерию разложимости 

$$А \text{ разложима } \Rightarrow \vec x(\theta) = 0 \Rightarrow \vec y = \theta\vec x_A$$

◼︎

<div style="border-left: 5px solid DodgerBlue; padding: 10px 20px; margin: 20px 0">

<b>Предложение 2.</b> Пусть \(A = ||a_{ij}||_{i,j=1}^n \geq 0\) — неразложимая матрица. Тогда: <br> <br>
<ol>
<li> Если \(\exists \vec x \geq 0:\) \((\rho\vec x - A\vec x) \geq 0\), \((\rho\vec x - A\vec x) \neq 0\), то \(\rho > \lambda_A\) </li> <br>

<li> Если \(\exists (\rho E - A)^{-1} \geq 0\), то \((\rho E - A)^{-1} > 0\) </li> <br>

<li> Если \(A \geq B\) и \(A \neq B\), то \(\lambda(A) > \lambda(B)\) </li> <br>

<li> Если \(C\) — собственная главная подматрица матрицы \(A\), то \(|\lambda_A E_C - C| > 0\) </li> <br>

<li> Пусть \(\varphi(\rho) = |\rho E - A|\), тогда \(\left.\dfrac{d}{d\rho}\varphi(\rho)\right|_{\rho = \lambda(A)} > 0\) (т.е. \(\lambda(A)\) имеет алгебраическую кратность \(1\), т.е. является простым корнем характеристического уравнения) </li>
</ol>
</div>

<div>
  <button class="proofbtn">*Доказательство.* </button>
  <div class="proof">

    1. Возьмем вектор Фробениуса-Перрона матрицы $A^T$. Пусть $A^T\vec p_A = \lambda_A \vec p_A$, $\vec p_A > 0$ (по теореме 4), тогда 

    $$0 < \left<\vec p_A, \rho\vec x - A\vec x\right> = \rho \left<\vec p_A, \vec x\right> - \left<A^T\vec p_A, \vec x\right> = (\rho - \lambda_A)\left<\vec p_A, \vec x\right>$$

    $\left<\vec p_A, \vec x\right> \geq 0$ $\Rightarrow$ $\rho > \lambda_A$

    *остальные утверждения доказываются аналогично*

  </div>
</div>
  
  
<div>
  <button class="proofbtn">Open Collapsible</button>

  <div class="proof">
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>

    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>

    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
  </div>
</div>
    
UPD1
