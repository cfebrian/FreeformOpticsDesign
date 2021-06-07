# FreeformOpticsDesign
The design process for free form optical systems (in particular reflective).


## Questions / Comments
* phi-polynomials refers to any polynomial that varies in two dimensions.

### It is difficult to tell if this problem is linear.  
If it is linear, then one should be able to arrive at linear combinations of the coefficients on various surfaces out of the plane of the pupil and reduce aberrations.  However, if it were linear, the *damped least squares* optimizer would easily arrive at a solution and *it does not*.  Therefore, one has to wonder:
1. Is it a linear system? (What are the conditions for linearity?  A certain amount of WFE?)
2. Do the Zernike polynomials away from the stop complete?  (Do they span the space of solutions?)
3. Do the Zernike polynomials away from the stop for an orthogonal set? (Are they redundant or degenerate?)

### The starting prescription ###
*Fuerschbach* indicates that a good, optimized starting point is necessary.  Whereas *Bauer* indicates that this is not the case.

### Does it matter if the surface with correction has power?
* Can corrector plates be implemented without power?  
* Is there something unique about applying these polynomials to surfaces that already have power (e.g. curved mirrors)?

### Is the impact of the phi-polynomials so unique that sensitivity must be explored for each system?
If this is the case, can one merely develop a sensitivity of aberrations for each surface and from there derive a solution?  Isn't that exactly how the optmizer in `OpticStudio` works?

### How patient should I be with the optimizer ###
I’m familiar with `OpticStudio` and there are various optimization modes that can run until they plateau or they can run “forever”.

### What is the appropriate merit function? ###
1. Seems that the *merit function* should change throughout the design process.  What are the right merit functions?
2. Experience with WFE and Spot Size indicate that these are not very good in a blind optimization.  
3. Should the *merit function* be Zernikes across the field?  Siedel aberrations? or ???

### Credits to Synopsis's `CodeV` imply... ###
1. Will this work equally well with Zemax's `OpticStudio`?

### A colleague mentioned a comparison with TMA's ###
The colleague said *"We looked into a FFS solution instead of a TMA.  We didn't see the advantage"*  However, several U of R references indicate a major improvement in size (and performance?).  Has a quantitatve comparison been performed?  When is there an advantage to FFS based designs? 
3. What do I need to know about `CodeV` to implement a similar methodology in `OpticStudio`

### Is there an inverse design process? ###
Why not take the design, with its aberrations, correct the field dependent aberrations and trace backwards to the *offending surfaces*?  Can not the prescriptions and/or sensitivities be determined in this manner?
