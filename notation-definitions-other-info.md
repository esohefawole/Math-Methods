# Notation, Definitions, and Other Useful Information (Part 1)

## Independent and Dependent Variables

- Independent variable: the variable that is changed or controlled; a variable whose variation <ins> does not depend</ins> on another variable  
    - Examples: $t, x, y, z, r, \theta, \phi$  
- Dependent variable: a variable whose value <ins> depends</ins> on other variables  
    - Examples: $u(t,x)$ or $c(t,r, \theta, z)$ where $u$ is used for temperature and $c$ is used for concentration. Both temperature and concentration depend on time (if the system is not at steady state) and position 

## Domain
- the range for the independent variables of the differential problem (in other words, the regions where the differential problem is defined)  
    - Examples:
        - $x \in [0,L]$ where $\in$ means "is an element of" $\big($ i.e. $0 \leq x \leq L \big)$
        - $r \in (0,a)$ meaning $0 < r < a$ (paretheses means the end values are not included in the range for $r$)
        - $\theta \in (0,\frac{\pi}{2}]$ meaning $0 < \theta \leq \frac{\pi}{2}$  

## Laplace operator or Laplacian: $\nabla^2$
- the <ins>divergence</ins> of the gradient of a scalar function
    - Gradient operator (del or nabla): $\nabla \equiv \frac{\partial}{\partial x} + \frac{\partial}{\partial y} + \frac{\partial}{\partial z}$ in cartesian coordinates 
- $\nabla^2 = \nabla \cdot \nabla = \frac{\partial}{\partial x} \big(\frac{\partial}{\partial x}\big) + \frac{\partial}{\partial y} \big(\frac{\partial}{\partial y}\big) + \frac{\partial}{\partial z} \big(\frac{\partial}{\partial z}\big)$ in cartesian coordinates
    - Examples: 
        - Cartesian: $\nabla^2 u = \nabla \cdot \nabla u = \frac{\partial}{\partial x} \big(\frac{\partial u}{\partial x}\big) + \frac{\partial}{\partial y} \big(\frac{\partial u}{\partial y}\big) + \frac{\partial}{\partial z} \big(\frac{\partial u}{\partial z}\big)$
        - Cylindrical: $\nabla^2 u = \nabla \cdot \nabla u = \frac{1}{r}\frac{\partial}{\partial r} \big(r \frac{\partial u}{\partial r}\big) + \frac{1}{r^2} \big(\frac{\partial^2 u}{\partial \theta^2}\big) + \big(\frac{\partial^2 u}{\partial z^2}\big)$
            - In many problems, it is known that the temperature or concentration <ins> does not depend on the polar angle </ins> $\underline{\theta}$, which means the problem is circularly or axially symmetric. In these cases: $\nabla^2 u = \frac{1}{r}\frac{\partial}{\partial r} \big(r \frac{\partial u}{\partial r}\big) + \big(\frac{\partial^2 u}{\partial z^2}\big)$
## Kronecker Delta
- a function of two, usually positive, variables that follows the following rules:
    - $\delta_{ij} = 0$ if $i \neq j$
    - $\delta_{ij} = 1$ if $i = j$

## Dirac Delta
- denoted (written) as $\delta(x-x_i)$ where $x$ can be any independent variable
- the Dirac delta function is like a <ins>concentrated source</ins> or a <ins>unit impusle force</ins> at $x=x_i$. It is so concentrated that integrating it with any continuous function <ins>"sifts"</ins> out the value at $x=x_i$.
    - Important properties
        - $\delta(x-x_i)$ equals 0 when $x \neq x_i$
        - $\delta(x-x_i)$ equals $\infty$ when $x=x_i$
        - $\delta(x-x_i) = \delta(x_i-x)$
        - $\int_{-\infty}^{\infty} \delta(x-x_i) dx_i =1$
        - <ins>Sifting property</ins>: $f(x_i) = \int_{-\infty}^{\infty} f(x) \delta(x-x_i) dx$

## Ordinary Differential Equation (ODE)
- a differential equation containing one or more functions of <ins> one independent variable</ins> and the <ins> derivatives</ins> of those functions
    - Examples:
        - $\frac{\partial^2 u}{\partial z^2} = 0$ where $u$ only depends on $z$
        - $\frac{\partial c}{\partial t} = Ac$ where $A$ is a constant and $c$ only depends on $t$

## Partial Differential Equation (PDE)
- involves <ins> two or more independent variables</ins>, an unknown function that depends on those independent variables, and <ins> partial derivatives</ins> of the unknown function with respect to the independent variables. This may also be referred to as a _Governing Equation_.
    - Examples:
        - <ins>Heat Equation</ins> (Cartesian): $\frac{\partial u}{\partial t} = K \nabla^2u = K\biggl[\frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} + \frac{\partial^2 u}{\partial z^2}\biggl]$ where $K$ is the thermal diffusivity.
            - the <ins>Heat Equation</ins> is a specific partial differential equation for temperature changes in a specified region.
        - <ins>Diffusion Equation</ins> (Cartesian): $\frac{\partial c}{\partial t} = D \nabla^2c = D\biggl[\frac{\partial^2 c}{\partial x^2} + \frac{\partial^2 c}{\partial y^2} + \frac{\partial^2 c}{\partial z^2}\biggl]$ where $D$ is the diffusion coefficient
            - the <ins>Diffusion Equation</ins> is a specific partial differential equation that describes the concentration of a quantity of interest in a specified region.
        - <ins>Wave Equation</ins> (second order PDE): $\frac{\partial^2 u}{\partial t^2} = c^2 \frac{\partial^2 u}{\partial z^2}$ 

## Initial Condition
- the condition when $t=0$. This condition can be across all domains of the problem or in specific portions of the domain (like piece-wise functions)
    - Examples:
        - $u(0,z) = 0$ (homogeneous)
        - $c(0,r,\theta,z) = c_o$ (inhomogeneous)
        - Piece-wise condition: In the domain $x \in [0,L]$
            - $u(0,x) = 
                \begin{cases} 
                    0 &0 \leq x \leq \frac{L}{2}\\\
                    T_1 &\frac{L}{2} \leq x \leq L
                \end{cases}$ 

## Boundary Conditions
- conditions at the spatial boundaries of the problem (here, $f$ can equal 0, a constant, or a function)
    - Examples:
        - Dirichlet: $u(t,0) = f$
        - Neumann: $\frac{\partial u}{\partial x} = f$
        - Robin: $\frac{k}{n}(\underline{n} \cdot \underline{\nabla}u + u = f)$ where $h$ is the heat transfer coefficient, $k$ is the thermal conductivity, and $\underline{n}$ is the normal vector which changes the sign of the boundary condition depending on which boundary is the focus.
            - at the $x=0$ boundary: $- \left.\frac{k}{h} \frac{\partial u}{\partial x}\right|_ {x=0} + u = f$
            - at the $x=L$ boundary: $\left.\frac{k}{h} \frac{\partial u}{\partial x}\right|_ {x=L} + u = f$
        - Periodic: $u(r,-\pi) = u(r,\pi)$ and $\frac{\partial u}{\partial \theta}(r,-\pi) = \frac{\partial u}{\partial \theta}(r,\pi)$
            - in a more general sense: $u(r,\theta) = u(r, \theta + 2\pi)$ and $\frac{\partial u}{\partial \theta}(r,\theta) = \frac{\partial u}{\partial \theta}(r,\theta + 2\pi)$
## Steady State
- A system is at steady state when there is <ins>no dependence on time</ins> (in other words, when the time derivative is equal to zero)
    - Example:
        - $\frac{\partial c}{\partial t} = D\biggl[\frac{\partial^2 c}{\partial x^2} + \frac{\partial^2 c}{\partial y^2} + \frac{\partial^2 c}{\partial z^2}\biggl] = 0$

## Homogeneity (and Inhomogeneity)
- Homogeneity: when a boundary condition or an initial condition <ins>is equal to zero</ins>. A PDE with no source term is also homogeneous.
    - Example:
        - $\frac{\partial u}{\partial t} = K\nabla^2 u = K\biggl[\frac{1}{r} \frac{\partial}{\partial r}\big( r \frac{\partial u}{\partial r}\big) + \frac{1}{r^2} \frac{\partial^2 u}{\partial \theta^2} + \frac{\partial^2 u}{\partial z^2}\biggl]$ 
        - $u(t,0) = 0$
- Inhomogeneity: when a PDE, boundary condition, or an initial condition <ins>is not equal to zero</ins>.
    - Example:
        - $\frac{\partial u}{\partial t} = K\nabla^2 u = K\biggl[\frac{1}{r} \frac{\partial}{\partial r}\big( r \frac{\partial u}{\partial r}\big) + \frac{1}{r^2} \frac{\partial^2 u}{\partial \theta^2} + \frac{\partial^2 u}{\partial z^2}\biggl] + \phi (t,r,\theta,z)$
        - $u(t,0) = f$
