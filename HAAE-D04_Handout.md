# Lifting Atmospheric Entry
**Version 24.0, Last Update: 30 Apr 2024**

*This handout was created exclusively for the course "Hypersonic Aerodynamics and Atmospheric Entry" at FH Aachen University of Applied Sciences by Prof. Dr. Bernd Dachwald. It contains copyright-protected material. Therefore, it may **not** be used for purposes other than educational and scientific work by students of FH Aachen University of Applied Sciences. It is not allowed to redistribute it in any form.*

![](figures/haae-d04_lifting_Seite_01.png)

Having analysed the atmospheric entry of a vehicle neglecting gravity and lift, we will now include these forces in our analysis. This will give us more accurate results. However, we will not get formulae describing the results, only "curves". We will then compare the numerical results graphically with our previous analytical results, and also compare the numerical results for different parameters. Finally, we will look at examples of entry-level vehicles.

# Lifting Entry Dynamics

![](figures/haae-d04_lifting_Seite_02.png)

The analysis of the motion of a space vehicle always starts with Newton's second law. This gives us the acceleration of the vehicle depending on the forces that act on it. As you can see in the images, these forces are drag, lift, and gravity. Unfortunately, Newton's laws are only valid in an inertial coordinate frame, while the motion of the entry vehicle is easier described in a rotating "wind coordinate system". This adds a bit to the complexity of our analysis. The unit vectors of the inertial coordinate system are $\hat{X}$, $\hat{Y}$, and $\hat{Z}$ (the latter is pointing out of the page). The unit vectors of the non-inertial wind coordinate system are $\hat{x}$, $\hat{y}$, and $\hat{z}$. $\hat{z}=\hat{Z}$. $\hat{x}$ is always along the velocity vector $V$, and $\hat{y} = \hat{z} \times \hat{x}$.

As you can see, the lift is perpendicular to the velocity direction and directed upwards, thus tending to decrease the flight path angle. Gravity, however, has a component in the velocity direction (which is decreasing the drag) and a component perpendicular to the velocity direction and directed downwards, thus tending to increase the flight path angle.

Note that the situation in both images is identical, the lower image one is just rotated by the flight path angle so that the local horizon is horizontal. Also note that the local horizon is always perpendicular to the radius vector.

---

We will now state the equations of motion in the wind coordinate system, considering that it is not inertial.

![](figures/haae-d04_lifting_Seite_03.png)

The right side of eq. (1) gives the inertial acceleration of a body that is moving with velocity $\vec{V}$ and (non-inertial) acceleration $\dot{\vec{V}}$ in the wind coordinate system. $\boldsymbol{\omega}$ is the angular velocity vector with which the wind coordinate system rotates with respect to the inertial coordinate system. The wind coordinate system rotates because the flight path angle changes ($\dot\gamma$), but also because the entry vehicle flies around the Earth ($\dot\theta$). According to the right hand rule, $\vec{\omega}$ points into the $\hat{z}$-direction for $\dot\theta+\dot\gamma > 0$. This way, one obtains the inertial acceleration as the right side of eq. (4). Eq. (5) is Newton's second law, applied to the given situation. In eq. (6), the forces are decomposed along the $\hat{x}$ and $\hat{y}$-direction. Eq. (7) shows the final result, where both the acceleration and the forces are decomposed along the $\hat{x}$ and $\hat{y}$-direction.

---

![](figures/haae-d04_lifting_Seite_04.png)

Since the $\hat{x}$-direction and the $\hat{y}$-direction are perpendicular to each other, the $\hat{x}$-terms are independent from the $\hat{y}$-terms and visa versa. Eq. (7) must be fulfilled in both directions, $\hat{x}$ and $\hat{y}$. Therefore, we can split the equation into one equation along the $\hat{x}$-direction and one along the $\hat{y}$-direction. What again was the angular velocity $\omega$ of the wind coordinate system with respect to the inertial frame? Remember that it has two contributions. One comes from the motion of the entry body around Earth. It is $\dot\theta=\frac{V\cos\gamma}{r}$ (you can find this formula for rotational motion in every collection of physical formulas). The other comes from the rotation of the entry body's velocity vector within the wind coordinate system. It is $\dot\gamma$. Having an expression for $\omega$, it can be deleted from eq. (9) and eq. (9) can be re-arranged to finally give eq. (13). This is a differential equation that gives us the time-change of $\gamma$ during entry. This is, however, not yet the final equation, because we want to replace the uncommon parameter $L/m$ by the common parameter $L/D$, the lift-to-drag ratio. Eq. (14) shows their dependency.

---

![](figures/haae-d04_lifting_Seite_05.png)

Eq. (15) is now our final differential equation for the change of the flight path angle. Remember that it results from eq. (9). But what about eq. (8)? Well, eq. (8) gives the differential equation for the change of the velocity, eq. (16). The third differential equation is eq. (17). It gives the change of altitude. Note that these three variables, $\gamma$, $V$, and $h$, are our system variables. They are the values in which we are interested. But if you look sharply to the three differential equations, you can see that they contain three other variables that change with time, $r$, $\rho$, and $g$.

---

![](figures/haae-d04_lifting_Seite_06.png)

All three of them can be expressed by equations that contain only the system variable $h$ and the four constants Earth radius $R_E$, ground density $\rho_0$, atmospheric scale height $H$, and gravitational surface acceleration $g_0$. On the next slide, we will insert those three equations into the three differential equations.

---

![](figures/haae-d04_lifting_Seite_07.png)

 Eqs. (21)-(23) are our final result. We have obtained three differential equations of first order. Unfortunately, they are coupled, i.e. all three variables occur in all three equations. Therefore, we can not solve this equation system analytically. We have to use a computer and a numerical method like the Runge-Kutta method that you certainly have heard of. Have another sharp look at the equations! They are complex, but the contain *only* three variables, $\gamma$, $V$, and $h$. The rest are constants. Now, what do we need to solve a differential equation system of first order? Yes, an initial value for each variable, i.e. $\gamma_0=\gamma(t=0)$, $V_0=V(t=0)$, and $h_0=h(t=0)$. The solution depends on those values and those are the three values that define our entry problem (... and whether or not our astronauts will survive).

---

![](figures/haae-d04_lifting_Seite_08.png)

Careful! An non-rotating Earth does not mean that the entry vehicle does not rotate araund the Earth, it does. It means that the rotation of the Earth during the short amount of time that is required for the atmospheric entry is negligible. A "real" rotating Earth would make everything just much more complicated without changing the solutions a lot (remeber that Earths surface velocity due to rotation depends strongly on latitude).

# Comparison of Ballistic and Lifting Entry

![](figures/haae-d04_lifting_Seite_09.png)

Before we solve the differential equation system numerically, note that the lift-to-drag ratio, $L/D$, and the ballistic coefficient, $\beta$, are not independent. They depend on the entry body shape as indicated in the above plot.

---

Let us first start with $L/D$, i.e. the calculation of the "real" entry of a ballistic entry vehicle:

![](figures/haae-d04_lifting_Seite_10.png)

The blue curve shows our analytical result. Remember: $\gamma_0=\text{const}$ (well, this was even one of our assumptions). The red curve shows that during the real entry, $\gamma$ constantly increases (gravity!) to a final value of $90^\circ$ (well, this is a vertical fall and you can not fall steeper than vertical).

---

![](figures/haae-d04_lifting_Seite_11.png)

Now let's compare the deceleration. It is even worse
 than in our analytical calculation. For the above noted conditions, the maximal deceleration increases from about 5.5 g to about 9 g.

---

![](figures/haae-d04_lifting_Seite_12.png)

The velocity-over-altitude curve shows that both curves are quite similar for high velocities but differ considerably for low velocities $\lesssim$ 1 km/s. Now, the entry vehicle does not get "stuck in the air" anymore but reaches the ground with the free-fall velocity.

---

![](figures/haae-d04_lifting_Seite_13.png)

The numerical integration can also show the variation of the variables over time, which was not possible for our analytic calculations, which were "time-free". Note the correspondence between velocity and deceleration.

---

![](figures/haae-d04_lifting_Seite_14.png)

The numerical integration can also show the variation of the variables over time, which was not possible for our analytic calculations, which were "time-free". Note the correspondence between velocity and deceleration.

---

![](figures/haae-d04_lifting_Seite_15.png)

Now, let's see what happens when we have a vehicle that generates some lift. The different curves are for different initial flight path angles. You can see that we get a "bump", i.e. the vehicle is carried upwards again, because the lift increases in denser atmospheric regions.

---

![](figures/haae-d04_lifting_Seite_16.png)

The maximal deceleration decreases with a decreasing flight path angle. Note that you have a phase of "weightlessness" during your entry (not so good for your stomach).

---

![](figures/haae-d04_lifting_Seite_17.png)

And the variation of the flight path angle for different initial flight path angles.

---

![](figures/haae-d04_lifting_Seite_18.png)

And the values over time.

---

![](figures/haae-d04_lifting_Seite_19.png)

This slide gives you also the downrange over time. Downrange is the flown distance on the ground. The curves for altitude over downrange show you the real trajectories but over a non-rotating Earth. The vehicle with the lowest $\gamma_0$ has the largest downrange. On the right side, you can see the heating rates and the total heat loads over time. Note that a large $\gamma_0$ produces a higher maximal heating rate but a lower total heat load.

---

![](figures/haae-d04_lifting_Seite_20.png)

Now, let's investigate the influence of $L/D$. You can see that a high $L/D$ carries the entry vehicle back to higher altitudes than it had with a higher velocity. Also, you can have many of those "bumps".

---

![](figures/haae-d04_lifting_Seite_21.png)

And the effect on the deceleration.

---

![](figures/haae-d04_lifting_Seite_22.png)

And the effect on the flight path angle. You can see that the final flight path angle depends on $L/D$. This is essentially your impact angle into the ground. Note that every time when $\gamma < 0$, you are carried upwards.

---

![](figures/haae-d04_lifting_Seite_23.png)

And again the values over time. Bumpy as hell.

---

![](figures/haae-d04_lifting_Seite_24.png)

And more values over time. The higher your $L/D$, the farther you fly. The curve for $L/D = 1.25$ in the lower left plot really looks like a skipping stone over a pond.

---

![](figures/haae-d04_lifting_Seite_25.png)

Now let's have a look to the influence of the ballistic coefficient. In this plot, it is quite minor.

---

![](figures/haae-d04_lifting_Seite_26.png)

Remember that, in our analytic calculation, the ballistic coefficient had no influence on the maximal deceleration. This plot shows that this is even true for our numerical calculation.

---

![](figures/haae-d04_lifting_Seite_27.png)

Same for the variation of the flight path angle.

---

![](figures/haae-d04_lifting_Seite_28.png)


And again the variation of several parameters over time.

---

![](figures/haae-d04_lifting_Seite_29.png)

In this plot you can see that the effect of the ballistic coefficient on the downrange is also minor, but there is quite some effect on the heating rate and the heat load. But we are prepared for this behavior thanks to the analytical calculations we did before.

---

![](figures/haae-d04_lifting_Seite_30.png)

What we can see from this plot: the higher the $L/D$, the higher the allowed flight path angle for a certain maximal deceleration.

---

![](figures/haae-d04_lifting_Seite_31.png)

This table shows you the peak radiation equilibrium temperature for different planets and flight path angles. The original source of this table is unknown. Be careful, at least one value seems to be wrong. Also, the assumed value for $\beta$ seems to be very low. This is a balloon-like entry body.

---

![](figures/haae-d04_lifting_Seite_32.png)

This diagram shows the entry corridor for a ballistic entry from orbit and from the Moon, as well as for a lifting entry with the Space Shuttle.

---

![](figures/haae-d04_lifting_Seite_33.png)

This diagram shows that you cannot fly at any altitude and velocity you like. If, at high altitudes, your velocity is too low, you will not produce enough lift to fly stationary. On the other hand, if you have a velocity that is too high at low altitudes, your stagnation pressure is too high and/or you have unacceptable aerodynamic heating. There is a (green) flight corridor, in which stationary flight is possible.

---

![](figures/haae-d04_lifting_Seite_34.png)

Another major advantage of lifting entry is that you have more control over your landing site and you have a higher landing accuracy. For a ballistic entry, your landing site is more or less completely determined by your de-orbit burn maneuver. During entry, also the unknown winds in the upper atmosphere will influence your landing site.

---

![](figures/haae-d04_lifting_Seite_35.png)

# Entry Vehicle Examples

![](figures/haae-d04_lifting_Seite_36.png)

This plot shows you the landing footprint for the Gemini capsules. It is approximately an ellipse with a length of about 550 km and a width of about 100 km. As you can see, most capsules hit the desired landing site quite accurately, but not all of them. Please consult Wikipedia, if you want to know what went wrong for those missions.

---

![](figures/haae-d04_lifting_Seite_37.png)

And some values for the Mercury capsules. You may again wish to consult Wikipedia to find out what went wrong with the capsules of Glenn and Carpenter.

---

![](figures/haae-d04_lifting_Seite_38.png)

---

![](figures/haae-d04_lifting_Seite_39.png)

As you can see, the $L/D$ is not constant but depends on the Mach number. As you can also see, the predictions are quite good.

---

![](figures/haae-d04_lifting_Seite_40.png)

And a last plot with real Space Shuttle values for altitude, velocity, and angle of attack (not flight path angle!). 

This ends my part of the course. I wish you a good time for Prof. Havermann's part.

# References

![](figures/haae-d04_lifting_Seite_41.png)
