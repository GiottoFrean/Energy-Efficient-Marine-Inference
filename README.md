# Energy-Efficient Marine Inference

This repository contains a collection of notebooks exploring energy-efficient machine learning and sensing strategies for low-disturbance marine observation. The focus is on approaches that minimize expensive resources such as movement, communication, and lighting. Below is an overview of each notebook:

- **A - Species inference from movement acoustics.ipynb**: This notebook investigates whether acoustic signatures produced by animal movement near a hydrophone array can be used to infer species presence. I generate simple synthetic data and train a basic classifier. This approach avoids disturbing light-sensitive animals and eliminates the need for energy-intensive lighting, enabling long-term autonomous monitoring.

	<img src="images/A%20-%20box_creature.gif" alt="box creature" width="360" />
	<img src="images/A%20-%20worm_creature.gif" alt="worm creature" width="360" />

- **B - Location optimization with Gaussian Processes.ipynb**: This notebook provides an overview of Gaussian Process (GP) optimization, emphasizing its efficiency in sample usage. In a marine setting, it could help identify areas of high animal density, where each sample is costly due to the need to raise and lower equipment.

	![GP progress](images/B%20-%20GP_progress.png)

- **C - Distributed event inference with communication costs.ipynb**: Here, I explore how a network of stationary receivers can detect events against a noisy background. For example, this could involve detecting whale presence using multiple sensors arranged in a grid. I implement a standard approach where signals are first aggregated between nodes, and then explore a communication-efficient variant where each node performs local inference and only transmits a message if a threshold is met. Aggregation of messages must account for accidental triggering.

	![Noise with signal](images/C%20-%20Noise_with_signal.png)
	![Array and signals](images/C%20-%20array_and_signals.png)
	<img src="images/C%20-%20score_grid.gif" alt="Score grid" width="360" />

- **D - Location optimization with an energy budget.ipynb**: This notebook extends the GP-based location optimization from Notebook B to explicitly consider energy or battery constraints. While standard GP optimization minimizes the number of samples, traveling between locations incurs a cost. I explore information-theoretic approaches and test methods for downweighting expected improvement based on travel distance.

	![GP with budget](images/D%20-%20gp_with_budget.png)
