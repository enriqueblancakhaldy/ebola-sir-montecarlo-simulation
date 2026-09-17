# Monte Carlo SIR Modeling of the 2014 Ebola Outbreak in Sierra Leone using Real Time Series Data.
The 2014 West Africa Ebola outbreak in Sierra Leone presented unprecedented epidemiological challenges, highlighting the need for robust mathematical modeling to track disease dynamics. This project implements a compartmental SIR model enhanced by Monte Carlo simulations to quantify transmission uncertainty and parameter variability using empirical outbreak data. By evaluating performance metrics like RMSE and Interval Coverage, the simulation assesses both the predictive capabilities and the structural limitations of standard epidemiological models.
<img width="863" height="552" alt="SIRebolaoutbreak" src="https://github.com/user-attachments/assets/64b34b21-f264-45a8-9518-7487df8fa3d4" />

* **RMSE** obtained: $1,245.14$.

* ## Model Limitations & Diagnostics

The simulation reveals significant divergence between the predicted trajectory and the empirical data, driven by three main factors:

* **Constant Transmission Rate ($\beta$):** Assuming a static transmission parameter fails to capture dynamic real-world shifts, such as public health interventions, behavioral adaptations, and changes in hospitalization rates over time.
* **Low Interval Coverage ($40\%$):** The $90\%$ confidence interval contains only $40\%$ of the observed empirical data points. This severe underestimation confirms that the basic stochastic SIR model fails to capture the full variance of the outbreak.
* **Heteroscedastic Uncertainty:** The outbreak dynamics display clear heteroscedasticity. While actual case fluctuations remain bounded, the model's simulated variance expands drastically over time, creating a wide uncertainty fan late in the timeline that misses the actual trend.

##Future work
* To address the limitations of the baseline SIR model and better capture the complex dynamics of the outbreak, future iterations of this project can focus on the following extensions:

* **Structural Compartmental Extensions (SEIR Framework):** Incorporating an *Exposed* ($E$) compartment to model the latent incubation period characteristic of the Ebola virus, where individuals are infected but not yet infectious.
* **Time-Varying Parameters:** Replacing static parameters with a dynamic, time-dependent transmission rate $\beta(t)$ to account for changing social behavior, intervention protocols, and quarantine measures.
* **Bayesian Inference & MCMC:** Transitioning from fixed parameters to a **Bayesian SIR framework**. By leveraging **Markov Chain Monte Carlo (MCMC)** sampling alongside probabilistic programming tools (e.g., PyMC or Stan), $\beta$ and $\gamma$ can be inferred as dynamic probability distributions updated continuously with empirical data, capturing systemic uncertainty with far greater accuracy.
