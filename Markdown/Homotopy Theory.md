# Homotopy Theory

### Homotopy groups
- **Def:** omit. 
- **Dependency of base point:**

### Homotopy Lifting Property & Homotopy Extending Property
- **Homotopy Lifting Property:** omit.
- **Borsuk's Lemma:** Any CW pair $(X,X')$ admits homotopy extending property.

    proof: Suppose $X$ is a CW complex, $X'$ is its subcomplex and $f':X'\to Y$ can extend to $f:X\to Y$. For any homotopy $F':X'\times I\to Y$ with initial map $f'$, we extend it by induction. 

    **Step 1:** For any vertex $x_0\in X^0 - X'$, we define 

    $$F(x_0,t) = f(x_0), \quad t\in [0,1]$$ 
    
    **Step 2:** Suppose we have extended the homotopy over the skeleton $X^n$. Now for any $(n+1)$-cell 

    $$\psi:D^{n+1}\to X$$ 

    The homotopy has been already defined on $S^n\times I$ and $D^{n+1}\times\{0\}$. To fill in the whole $D^{n+1}\times I$, we use the fact that there is a nice retraction (projection) 

    $$r:D^{n+1}\times I\to(S^n\times I)\cup(D^{n+1}\times\{0\})$$ 

    The following figure provides a nice illustration.

    <p align="center">
        <img src="./Figures/borsuk_lemma.png" alt="Homotopy Extension Property Illustration" width="200"/>
    </p>

    Thus we can extend the homotopy to any $(n+1)$-cell, so as $X^{n+1}$. 