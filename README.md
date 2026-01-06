# Energy-Efficient Marine Inference

Collection of notebooks exploring energy-efficient machine learning and sensing strategies for low-disturbance marine observation. I focus approaches which minimize expensive resources like movement, communication and lighting. Here is an overview of each notebook:

- **A - Species inference from movement acoustics.ipynb**: I examine whether acoustic signatures created by movement close to a hydrophone array could be used to infer the species present. I make some very simple synthetic data and train a simple classifier. The benefit is you don't distube light-sensitive animals and you also avoid expensive lighting. This could enable an autonomous robot to monitor for a long period of time.

	<img src="images/A%20-%20box_creature.gif" alt="box creature" width="360" />
	<img src="images/A%20-%20worm_creature.gif" alt="worm creature" width="360" />

- **B - Location optimization with Gaussian Processes.ipynb**: This notebook just reviews Gaussian Process optimization. A major benefit is the efficiency with which samples are used. In the marine context you might want to find areas of high animal density, but each sample is very expensive as you need to raise and lower the equipment. 

	![GP progress](images/B%20-%20GP_progress.png)

- **C - Distributed event inference with communication costs.ipynb**: In this notebook I look at how a set of stationary receivers can infer whether an event has occured against a noisy background. In the marine context you could be trying to detect the presence of a whale using multiple sensors placed in a grid. I come up with a standard approach where the signals are first aggregated between nodes before briefly exploring a communication-efficient alternative where each node performs it's own inference and only sends a message when a certain trigger threshold is met. Of course, results need to be aggregated somehow in a way which deals with the inherent noise.

	![Noise with signal](images/C%20-%20Noise_with_signal.png)
	![Array and signals](images/C%20-%20array_and_signals.png)
	<img src="images/C%20-%20score_grid.gif" alt="Score grid" width="360" />

- **D - Location optimization with an energy budget.ipynb**: Here I wonder about extending the GP-based location selection from notebook B to explicitly include energy/battery budgets. Plain GP optimization is good for minimizing the number of samples, but what if travelling from one sample to the next has a cost? I review some information theory and then explore whether the distance can be used to downweight expected improvement. 

	![GP with budget](images/D%20-%20gp_with_budget.png)
