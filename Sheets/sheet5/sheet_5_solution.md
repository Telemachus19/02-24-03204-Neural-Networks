---
title: Sheet 5 Solution
author: Ahmed Ashraf Mohamed, 2103134
---

# Question 1

$$
    \begin{gathered}
        J = \cos(u) \\ 
        u = u_1 + u_2 = \sin(x^2) + 3x^2 \\ 
        u_1 = \sin(t), u_2 = 3t \\
        t = x^2 
    \end{gathered}
$$
$$
    \begin{aligned}
        \frac{\delta t}{\delta x} &= 2x \\ 
        \frac{\delta u_2}{\delta t} &= 3 \\
        \frac{\delta u_1}{\delta t} &= \sin(t) \\ 
        \frac{\delta u}{\delta t} &= \frac{\delta u_1}{\delta t} + \frac{\delta u_2}{\delta t} \\ 
        \frac{\delta t}{\delta x} &= 2x\\
        \frac{\delta J}{\delta x} &= -\sin(u) \frac{\delta u}{\delta t} \cdot \frac{\delta t}{\delta x} \\
                                  &= -\sin(u) (\frac{\delta u_1}{\delta t} \cdot \frac{\delta t}{\delta x} + \frac{\delta u_2}{\delta t} \cdot \frac{\delta t}{\delta x}) \\
                                  &= -\sin(\sin(x^2)+3x^2)(\sin(x^2) \cdot 2x + 3 \cdot 2x) \\ 
                                  &= -\sin(\sin(x^2)+3x^2)(2x \cos (x^2) + 6x)
    \end{aligned}
$$

# Question 2

$$
    \begin{gathered}
        J = x^2 + y^2 +z^2 \\ 
        x = u + v \\
        y = u - v\\
        z = u^2 + v^2 \\
    \end{gathered}
$$

Forward Path

$$
    \begin{aligned}
        J &= (u + v)^2 + (u -v)^2 + (u^2 + v^2)^2 \\
          &= u^4 + v^4 + 2u^2 + 2v^2 + 2u^2 v^2 \\
    \end{aligned}
$$

Back-propagation

$$
    \begin{aligned}
        \frac{\delta x}{\delta u} &= 1 \\ 
        \frac{\delta y}{\delta u} &= 1 \\
        \frac{\delta z}{\delta u} &= 2u \\
        \frac{\delta J}{\delta u} &= 2x \frac{\delta x}{\delta u} + 2y \frac{\delta y}{\delta u} + 2z \frac{\delta z}{\delta u} \\
                                  &= 2(u+v) (1) + 2(u-v) (1) + 2(u^2 + v^2) (2u) \\ 
                                  &= 4u^3 + 4uv^2 + 4u^3
    \end{aligned}
$$

---

$$
    \begin{aligned}
    \frac{\delta x}{\delta v} &= 1 \\ 
    \frac{\delta y}{\delta v} &= -1 \\
    \frac{\delta z}{\delta v} &= 2v \\
    \frac{\delta J}{\delta v} &= 2x \frac{\delta x}{\delta v} + 2y \frac{\delta y}{\delta v} + 2z \frac{\delta z}{\delta v} \\
                              &= 2(u+v) (1) + 2(u-v) (-1) + 2(u^2 + v^2) (2v) \\ 
                              &= 4v^3 + 4vu^2 + 4v
    \end{aligned}
$$
# Question 3

$$
    \begin{aligned}
    f(x,y) &= x^3 -y^2 +3xy^2 \\
    \frac{\delta x}{\delta u} &= (2x)^{-1}\\
    \frac{\delta y}{\delta u} &= -(2y)^{-1}\\
    \frac{\delta f}{\delta u} &= 3x^2 \cdot \frac{\delta x}{\delta u} - 2y \frac{\delta y}{\delta u} + 3 (\frac{\delta x}{\delta u}) y^2 + 3 (2y \frac{\delta y}{\delta u})x \\
    &= \frac{3}{2} x + \frac{3}{2} \frac{y^2}{x} - 3 - \frac{3}{2}y 
    \end{aligned}
$$

$$
    \begin{aligned}
    f(x,y) &= x^3 -y^2 +3xy^2 \\
    \frac{\delta x}{\delta u} &= (2x)^{-1}\\
    \frac{\delta y}{\delta u} &= -(2y)^{-1}\\
    \frac{\delta f}{\delta u} &= 3x^2 \cdot \frac{\delta x}{\delta u} - 2y \frac{\delta y}{\delta u} + 3 (\frac{\delta x}{\delta u}) y^2 + 3 (2y \frac{\delta y}{\delta u})x \\
    &= \frac{3}{2} x + \frac{3}{2} \frac{y^2}{x} - 3 - \frac{3}{2}y 
    \end{aligned}
$$

$$
 \begin{aligned}
    f(x,y) &= x^3 -y^2 +3xy^2 \\
    \frac{\delta x}{\delta v} &= (2y)^{-1}\\
    \frac{\delta y}{\delta u} &= (2x)^{-1}\\
    \frac{\delta f}{\delta v} &= 3x^2 \cdot \frac{\delta x}{\delta v} - 2y \frac{\delta y}{\delta v} + 3 (\frac{\delta x}{\delta v}) y^2 + 3 (2y \frac{\delta y}{\delta v})x \\
    &= \frac{3}{2} \frac{x^2}{y} - \frac{3}{2} \frac{y^2}{x} + \frac{9}{2}y 
    \end{aligned}
$$

# Question 4

$$
    \begin{gathered}
        J = \hat{y} \ln(y + (1-\hat{y})) - \ln(1-y) \\
        y = \dfrac{1}{1 + e^{-\alpha}}\\
        \alpha = \sum_{i = 0}^{n} \theta_i x_i
    \end{gathered}
$$

forward path:

$$
    \begin{aligned}
        J &= \hat{y} \ln(y + (1-\hat{y})) - \ln(1-y) \\
          &= \hat{y} \ln\left(\frac{1}{1 + e^{-\sum_{i =0}^{n} \theta_i x_i}} + (1- \hat{y})\right) - \ln\left(1 - \frac{1}{1 + e^{-\sum_{i =0}^{n} \theta_i x_i}} \right)
    \end{aligned}
$$

back-propagation

$$
    \begin{aligned}
        \frac{\delta \alpha}{\delta \theta} &= \sum_{i = 0}^{n} x_i \\ 
        \frac{\delta y}{\delta \alpha} &=  y(1 -y)\\
        \frac{\delta J}{\delta \theta} &= \hat{y} \left( \dfrac{ \dfrac{\delta y}{\delta \theta}  }{ y + (1 - \hat{y})}  \right) + \dfrac{\dfrac{\delta y}{\delta \theta}}{1-y} \\ 
        &=  \hat{y} \left( \dfrac{ y(1-y) \sum_{i = 0}^{n} x_i }{ y + (1 - \hat{y})}  \right) + \dfrac{y(1-y) \sum_{i = 0}^{n} x_i}{1-y} \\ 
        &= \hat{y} \left( \dfrac{ \dfrac{1}{1 + e^{-\sum_{i =0}^{n} \theta_i x_i}}(1-\dfrac{1}{1 + e^{-\sum_{i =0}^{n} \theta_i x_i}}) \sum_{i = 0}^{n} x_i }{ \dfrac{1}{1 + e^{-\sum_{i =0}^{n} \theta_i x_i}} + (1 - \hat{y})}  \right) + \dfrac{1}{1 + e^{-\sum_{i =0}^{n} \theta_i x_i}} \sum_{i = 0}^{n} x_i  
    \end{aligned}
$$
