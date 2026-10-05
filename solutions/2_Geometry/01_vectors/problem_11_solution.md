## Question

Decompose $u=(3,4)$ into components parallel and perpendicular to $v=(1,2)$, perform both requested checks, and explain why they are independent.

## Solution

The parallel component is the projection:

$$u_{\parallel}=\frac{u\cdot v}{v\cdot v}v=\frac{11}{5}(1,2)=\left(\frac{11}{5},\frac{22}{5}\right).$$

Subtracting it from $u$ gives

$$u_{\perp}=u-u_{\parallel}=\left(\frac45,-\frac25\right).$$

The reconstruction check is

$$u_{\parallel}+u_{\perp}=\left(\frac{15}{5},\frac{20}{5}\right)=(3,4)=u,$$

while the orthogonality check is

$$u_{\perp}\cdot v=\frac45-\frac45=0.$$

Reconstruction checks that no component of $u$ was lost; the dot product separately checks that the residual has the required perpendicular direction. Either condition alone would not establish both facts.
