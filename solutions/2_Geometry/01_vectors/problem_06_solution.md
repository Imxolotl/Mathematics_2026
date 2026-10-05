## Question

Project $u=(4,2)$ onto $v=(1,1)$, compute the residual $r$, verify $r\cdot v=0$, and explain the result geometrically.

## Solution

Using the projection formula,

$$\operatorname{proj}_v u=\frac{u\cdot v}{v\cdot v}v=\frac{6}{2}(1,1)=(3,3).$$

Thus

$$r=u-\operatorname{proj}_v u=(4,2)-(3,3)=(1,-1),$$

and the requested calculation is

$$r\cdot v=(1,-1)\cdot(1,1)=1-1=0.$$

The projection $(3,3)$ is parallel to $v$, so it is the component of $u$ in the projection direction. Subtracting this parallel component leaves the perpendicular component $r$. The zero dot product verifies geometrically that $r$ is perpendicular to the direction $v$.
