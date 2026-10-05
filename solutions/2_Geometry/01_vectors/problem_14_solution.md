## Question

For $P=(4,1)$ and the line through the origin in direction $v=(1,2)$, find the closest point and distance using projection, and verify the relevant perpendicularity.

## Solution

The closest point is the projection of $P$ onto the line:

$$Q=\operatorname{proj}_v P=\frac{P\cdot v}{v\cdot v}v=\frac65(1,2)=\left(\frac65,\frac{12}{5}\right).$$

The displacement from the closest point to $P$ is

$$P-Q=\left(\frac{14}{5},-\frac75\right),$$

so the distance is

$$\|P-Q\|=\sqrt{\frac{196+49}{25}}=\frac{7}{\sqrt5}.$$

The perpendicularity check is

$$(P-Q)\cdot v=\left(\frac{14}{5},-\frac75\right)\cdot(1,2)=\frac{14}{5}-\frac{14}{5}=0.$$

Thus the displacement from $Q$ to $P$ is perpendicular to the line direction. A perpendicular segment is the shortest segment from a point to a line, so this also explains why $Q$ is the closest point.
