# Analysis for 5D ECM
Jupter notebooks for [k-resolved ECM](https://doi.org/10.1016/j.ultramic.2023.113886) analysis on 5D STEM dataset

5D data set are record as $I(t,x,y,k_x,k_y)$ or $I(t,r,k)$ where $r$ and $k$ indicates real and k space pixels. To extract spatial and wave-vector resolved relaxation time $\tau(r,k)$, we calculate time correlation function for each pixel:

$$ g_2(t,r,k) = \frac{\left\langle I(t',r,k)I(t+t',r,k)\right\rangle_{t'}}{\left\langle I(t,r,k)\right\rangle_t^2} $$

Relaxation times $\tau(r,k)$ are then extracted by fitting $g_2$ against KWW expression:

$$ g_2(t,r,k) = 1 + A\exp\left\lbrack -2\left\lparen\frac{t}{\tau(r,k)}\right\rparen^{\beta(r,k)}\right\rbrack $$

This process is preceded by aligning the data for sample drift and then typically polar unwrap the k axes.

Python package requirements: python==3.7, scipy==1.7.3, hyperspy==1.7.3, pyxem==0.14.2, seq-io==0.10, zarr==2.12.0, dask-jobqueue==0.7.4, matplotlib==3.5.3
