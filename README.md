# Hidden-Markov-Map-Matching-Through-Noise

In the first phase of project, i implement a *denoising algorithm* to do map matching algorithm that uses a **Hidden Markov Model** (HMM) to find the most likely road route represented by a time-stamped sequence of latitude/longitude pairs.
  In many urban areas and the places with tall towers, the GPS signal gets too noisy! This is the reason of why when you open "google maps", you see your current location with a blue circle around it. The radius of this circle shows the accuracy of your location. Sometimes, this radius is around 10m and in other areas, it goes in scale of km, making the GPS location totally unstable and unreliable! This amount of noise makes it impossible to use the data for any kind of analysis. In "ride hailing" applications like Uber, many of functionalities rely on the accuracy of GPS data. E.g. ETA estimation (Estimated time of arrival) is highly dependent on the accuracy of GPS data.
  
The modeling of transition and emission probabilites, 

**Emission probability :**

$$ p\left(z_t \mid r_i\right)=\frac{1}{\sqrt{2 \pi} \sigma_z} e^{-0.5\left(\frac{\left\|z_t-x_{t, i}\right\|_{\text {great circle }}}{\sigma_z}\right)^2} $$


**Transition Probability:**

$$ p\left(d_t\right)=\frac{1}{\beta} e^{-d_t / \beta} $$

Here

$$
d_t=\mid \mid z_t-z_{t+1}\mid_{\text {great circle }}-\mid x_{t, i^*}-x_{t+1, j} \cdot\mid_{\text {route }}\mid 
$$


<p style="color:yellow;"> Note:  This probability modeling is adopted from "Hidden Markov Map Matching Through Noise and Sparseness ,Paul Newson and John Krumm  Microsoft Research", where slight changes to use Transition and emission
probability functions.</p>

At the picture below, noisy points are marked in yellow, while the others are denoised:

![Screenshot 2024-01-30 195628](https://github.com/Amirabbas-Afzali/Hidden-Markov-Map-Matching-Through-Noise/assets/102149705/52a3016d-bdc5-427d-8cac-39e0c3468eb6)
