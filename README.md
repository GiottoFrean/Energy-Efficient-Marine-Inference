# Energy-Efficient Marine Inference

This repository contains a collection of notebooks exploring energy-efficient machine learning and sensing strategies for low-disturbance marine observation. The focus is on approaches that minimize expensive resources such as movement, communication, and lighting. Below is an overview of each notebook:

- **A - Species inference from movement acoustics.ipynb**: This notebook investigates whether acoustic signatures produced by animal movement near a hydrophone array can be used to infer species presence. I generate simple synthetic data and train a basic classifier. This approach avoids disturbing light-sensitive animals and eliminates the need for energy-intensive lighting, enabling long-term autonomous monitoring.

	<img src="images/A%20-%20box_creature.gif" alt="box creature" width="360" />
	<img src="images/A%20-%20worm_creature.gif" alt="worm creature" width="360" />

- **B - Location optimization with Gaussian Processes.ipynb**: This notebook provides an overview of Gaussian Process (GP) optimization, emphasizing its efficiency in sample usage. In a marine setting each sample of something like animal density is costly due to the need to raise and lower equipment.

	<img src="images/B%20-%20GP_progress.png" alt="GP progress" width="720" />

- **C - Distributed event inference with communication costs.ipynb**: Here, I explore how a network of stationary receivers can detect events against a noisy background. For example, this could involve detecting whale presence using multiple sensors arranged in a grid. I implement a standard approach where signals are first aggregated between nodes, and then explore a communication-efficient variant where each node performs local inference and only transmits a message if a threshold is met. Aggregation of messages must account for accidental triggering.

	<img src="images/C%20-%20Noise_with_signal.png" alt="Noise with signal" width="720" />

	<img src="images/C%20-%20array_and_signals.png" alt="Array and signals" width="720" />

	<img src="images/C%20-%20score_grid.png" alt="Score grid" width="360" />

- **D - Location optimization with an energy budget.ipynb**: This notebook extends the GP-based location optimization from Notebook B to explicitly consider energy or battery constraints. While standard GP optimization is efficient in the number of samples, traveling between locations might incur some cost in some scenarios. I explore information-theoretic approaches and test methods for downweighting expected improvement based on travel distance.

	<img src="images/D%20-%20gp_with_budget.png" alt="GP with budget" width="720" />

- **E - Optimization with rare events.ipynb**: This notebook looks at the challenge of nagivating to an area with a high number of events per unit time when you only see events rather than the underlying code. Consider an autonomous robot trying to find the point of highest animal density in a particular area. The underlying data comes from a continuous version of the multi-armed bandit problem, or an Inhomogenous Poisson Process. I test out a solution where the events over time are turned into a events-per-unit-time plot as the robot moves, and from that plot I look at reconstructing the full multidimensional function.

	<img src="images/E%20-%20path_true_function.png" alt="Score grid" width="360" />

	<img src="images/E%20-%20samples_path_example.png" alt="Events over time and the true density" width="720" />
	
	<img src="images/E%20-%20path_inferred_function.png" alt="Score grid" width="360" />
