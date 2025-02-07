---
layout: post
title: Note 1 - 13/02/2023
parent: Calculus II
nav_order: 1
---

{% include toc.md %}

## Review integrations technics of one-variable functions

### I. Subtitution Rule

$$
    \int f(g(x))g'(x)~dx = \int f(u)~du ~~\text{with}~ u=g(x)
$$

_Example:_

Evaluate the integral: $\mathrm{I} = \displaystyle \int \sin x \sin(\cos x)~dx$

* First approach:

    $\displaystyle \text{Let}~ u=\cos x \Rightarrow du=-\sin x~dx$

    $\displaystyle \Rightarrow \text{I} = - \int \sin u ~du = \cos u + C = \cos(\cos x) + C$

* Second approach:

    $\displaystyle \frac{d}{dx}(\cos x) = -\sin x \Rightarrow d(\cos x) = -\sin x ~dx$

    $\displaystyle \Rightarrow \mathrm{I} = - \int \sin(\cos x) ~d(\cos x) = \cos(\cos x) + C$

### II. Integration by Parts

Let $u=f(x)$ and $v=g(x)$ then

$$
    \int u~dv = uv - \int v~du
$$

_Example:_

Evaluate the given integral: $\displaystyle \mathrm{I} = \int \frac{xe^{2x}}{(1+2x)^2} ~dx$

**Solution**:

$\displaystyle \begin{cases} 
    u = xe^{2x} \\
    dv = \dfrac{dx}{(1+2x)^2}
\end{cases} \Rightarrow \begin{cases}
    du = (1+2x)e^{2x}~dx\\
    \text{choose}~ v=\dfrac{-1}{2(1+2x)}
\end{cases}$

$\displaystyle \Rightarrow \mathrm{I} = \frac{-xe^{2x}}{2(1+2x)} + \frac{1}{2} \int e^{2x} ~dx = \frac{-xe^{2x}}{2(1+2x)} + \frac{e^{2x}}{4} + C$

### III. Additional methods

* Evaluate: $\displaystyle \mathrm{I} = \int \dfrac{ax+b}{Ax^2+Bx+C} dx \ \text{with} \ A \neq 0$
    
    Let $\Delta = B^2-4AC$, we consider three cases:
    
    * Case 1: $\Delta = 0$
    
        $\Rightarrow Ax^2+Bx+C=0$ has one real root $\alpha.$

        $\displaystyle \therefore \mathrm{I} = \int \frac{ax+b}{A(x-\alpha)^2} ~dx = \int \left[ \frac{E}{(x-\alpha)^2} + \frac{F}{x-\alpha} \right] ~dx$

        $\displaystyle \Rightarrow \mathrm{I} = -\frac{E}{x-\alpha} + F\ln \lvert x-\alpha \rvert + C$

        ($E$ and $F$ are constant values)
        
        _Example:_
        
        Evaluate the given integral: $\displaystyle \mathrm{I} = \int \frac{x+3}{x^2+2x+1} ~dx$
        
        **Solution**:
        
        In scratch: $\dfrac{x+3}{x^2+2x+1} = \dfrac{x+3}{(x+1)^2} = \dfrac{A}{(x+1)^2} + \dfrac{B}{x+1} = \dfrac{Bx+A+B}{(x+1)^2}$
        
        Comparing the coefficients: $\begin{cases}
            B=1 \\
            A+B=3
        \end{cases} \Rightarrow \begin{cases}
            A=2 \\
            B=1
        \end{cases}$
        
        So: $\dfrac{x+3}{x^2+2x+1}=\dfrac{2}{(x+1)^2} + \dfrac{1}{x+1}$
        
        $\therefore \displaystyle \mathrm{I} = \int \left[\frac{2}{(x+1)^2} + \frac{1}{x+1}\right] ~dx = -\frac{2}{x+1}+\ln \lvert x+1 \rvert +C$

    * Case 2: $\Delta > 0$

        $\Rightarrow Ax^2+Bx+C=0$ has two real roots $x_1$ and $x_2.$

        $\displaystyle \therefore \mathrm{I} = \int \frac{ax+b}{A(x-x_1)(x-x_2)} ~dx = \int \left(\frac{E}{x-x_1} + \frac{F}{x-x_2}\right) ~dx$

        $\Rightarrow \mathrm{I} = E\ln \lvert x-x_1 \rvert  + F\ln \lvert x-x_2 \rvert  + C$
        
        _Example:_
        
        Evaluate the given integral: $\displaystyle \mathrm{I} = \int_0^1 \frac{2}{2x^2+3x+1} ~dx$
        
        **Solution**:
        
        In scratch: $\dfrac{2}{2x^2+3x+1} = \dfrac{2}{(x+1)(2x+1)} = \dfrac{A}{x+1} + \dfrac{B}{2x+1}$
        
        $A(2x+1)+B(x+1)=(2A+B)x+A+B$
        
        Comparing the coefficents: $\begin{cases}
            2A+B=0 \\
            A+B=2
        \end{cases} \Rightarrow \begin{cases}
            A=-2 \\
            B=4
        \end{cases}$
        
        So: $\dfrac{2}{2x^2+3x+1} = \dfrac{4}{2x+1} - \dfrac{2}{x+1}$
        
        $\therefore \displaystyle \mathrm{I} = \int_0^1 \left(\frac{4}{2x+1} - \frac{2}{x+1}\right)~dx = \left[2\ln \lvert 2x+1\rvert - 2\ln \lvert x+1 \rvert \right] \bigg \vert _0^1 = 2\ln\frac{3}{2}$

    * Case 3: $\Delta < 0$

        $\Rightarrow Ax^2+Bx+C=0$ has no real root.

        $\displaystyle \therefore \mathrm{I} = \int \left(\frac{E(\text{denominator})'}{Ax^2+Bx+C} + \frac{F}{(x+\alpha)^2+\beta^2} \right) ~dx$

        $\Rightarrow \mathrm{I} = E\ln \lvert \text{denominator} \rvert  + \dfrac{F}{\beta} \arctan\left(\dfrac{x+\alpha}{\beta}\right) + C$

        _Example:_
        
        Evaluate the given integral: $\displaystyle \mathrm{I} = \int_0^1 \frac{x}{x^2+4x+13} ~dx$
        
        **Solution**:
        
        $$
        \begin{align}
        \mathrm{I} &= \int_0^1 \frac{x}{(x+2)^2+3^2}~dx \\ 
        &= \int_0^1 \frac{x+2}{(x+2)^2+3^2}~dx - \int_0^1 \frac{2}{(x+2)^2+3^2}~dx \\
        &= \left.\frac{1}{2} \ln \lvert x^2+4x+13 \rvert \right \vert _0^1 - \left.\frac{2}{3}\arctan\left(\frac{x+2}{3}\right) \right \vert _0^1 \\
        &= \frac{1}{2} \ln\frac{18}{13} - \frac{2}{3}\left(\frac{\pi}{4}-\arctan\frac{2}{3}\right)
        \end{align}
        $$
