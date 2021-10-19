---
layout: page
title: §2. Продуктивные матрицы
---



> **Теорема 1.** Пусть $$D = \|d_{ij}\|_{i,j=1}^n$$, $$d_{ij} \leq 0$$ при $$i \neq j$$. Тогда следующие свойства эквивалентны:
>
> 1. $$\exists \vec x \geq 0:$$ $$D\vec x > 0$$
> 
> 2. $$\forall \vec w \geq 0\ \exists \vec x \geq 0:\ D\vec x = \vec w$$
> 
> 3. *условия Хокинса-Саймона*: 
> 
> $$\Delta_k = \det\begin{Vmatrix}
d_{11} & \dots & d_{1k} \\
\vdots & \ddots & \vdots \\
d_{k1} & \dots & d_{kk}
\end{Vmatrix} > 0 \quad\quad k=1,\dots,n$$
> 
> 4. $$\forall\ 1 \leq i_1 < \dots < i_k \leq n$$ ($$k=1,\dots,n$$) 
> 
> $$\det\begin{Vmatrix}
d_{i_1i_1} & \dots & d_{i_1i_k} \\
\vdots & \ddots & \vdots \\
d_{i_ki_1} & \dots & d_{i_ki_k}
\end{Vmatrix} > 0$$



▶︎ $$\dots$$ ◼︎

*Замечание.* Рассмотрим статическую модель Леонтьева $$\vec x = A\vec x + \vec w$$ в тривиальном случае ($$n=1$$). Пусть $$x$$ &mdash; объём производства, $$a_{11}x$$ &mdash; производственные затраты, $$w$$ &mdash; конечный выпуск. Тогда

$$x = a_{11} + w \quad \Leftrightarrow \quad (1-a_{11})x = w$$

Условие продуктивности:

$$1 > a_{11}$$





> **Теорема 1'.** К свойствам (1)&ndash;(4) теоремы 1 можно добавить следующие:
> 
> 5. $$\exists \vec p \geq 0:\ D^T\vec p > 0$$
> 
> 6. $$\forall \vec\pi \geq 0\ \exists \vec p \geq 0:\ D^T\vec p = \vec\pi$$
> 
> 7. все последовательные главные миноры матрицы $$D^T$$ положительны
> 
> 8. все главные миноры матрицы $$D^T$$ положительны
> 
> 9. $$\exists D^{-1} \geq 0$$



▶︎ $$\dots$$ ◼︎
