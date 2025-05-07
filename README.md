# Flappy-bird-Reinforcement-learning

A Python implementation of Flappy Bird where an AI learns to play using the NEAT (NeuroEvolution of Augmenting Topologies) algorithm. Built using Pygame and neat-python.

---

## 📁 Project Structure

```
Flappy-Bird-AI/
├── __pycache__/                # Compiled bytecode files
├── AI_mode.py                 # Run trained AI to play the game
├── Base.py                    # Ground scrolling logic
├── Bird.py                    # Handles bird physics and movement
├── Pipe.py                    # Manages pipes and collisions
├── config-feedforward.txt     # NEAT configuration
├── images/                    # Sprite assets for bird, pipes, base, background
├── main.py                    # Playable version for humans
├── training.py                # Trains the AI using NEAT
├── winner_genome.pkl          # Saved best genome after training
├── README.md                  # This file
├── requirements.txt           # Required Python packages
```

---

## ⚙️ Installation

### ✅ Prerequisites

- Python 3.7 or higher
- `pip` package installer

### 📦 Install Dependencies

```bash
pip install -r requirements.txt
```

If `requirements.txt` is empty, install manually:

```bash
pip install pygame neat-python
```

---

## 🎮 How to Play

### Human Mode

```bash
python main.py
```

**Controls:**
- Press `SPACE` to make the bird jump
- Press `R` to restart after a crash

---

## 🧠 Train the AI

```bash
python training.py
```

- Trains the AI using NEAT
- A population of birds evolves to maximize their survival time
- Saves the best-performing genome to `winner_genome.pkl`

---

## 🤖 Run AI Mode

```bash
python AI_mode.py
```

- Loads `winner_genome.pkl`
- Lets the best AI play the game automatically

---

## 🧬 NEAT Configuration

Contents of `config-feedforward.txt`:

```
[NEAT]
fitness_criterion     = max
fitness_threshold     = 100
pop_size              = 20
reset_on_extinction   = False

[DefaultGenome]
# node activation options
activation_default      = tanh
activation_mutate_rate  = 0.0
activation_options      = tanh

# node aggregation options
aggregation_default     = sum
aggregation_mutate_rate = 0.0
aggregation_options     = sum

# node bias options
bias_init_mean          = 0.0
bias_init_stdev         = 1.0
bias_max_value          = 30.0
bias_min_value          = -30.0
bias_mutate_power       = 0.5
bias_mutate_rate        = 0.7
bias_replace_rate       = 0.1

# genome compatibility options
compatibility_disjoint_coefficient = 1.0
compatibility_weight_coefficient   = 0.5

# connection add/remove rates
conn_add_prob           = 0.5
conn_delete_prob        = 0.5

# connection enable options
enabled_default         = True
enabled_mutate_rate     = 0.01

feed_forward            = True
initial_connection      = full

# node add/remove rates
node_add_prob           = 0.2
node_delete_prob        = 0.2

# network parameters
num_hidden              = 0
num_inputs              = 3
num_outputs             = 1

# node response options
response_init_mean      = 1.0
response_init_stdev     = 0.0
response_max_value      = 30.0
response_min_value      = -30.0
response_mutate_power   = 0.0
response_mutate_rate    = 0.0
response_replace_rate   = 0.0

# connection weight options
weight_init_mean        = 0.0
weight_init_stdev       = 1.0
weight_max_value        = 30
weight_min_value        = -30
weight_mutate_power     = 0.5
weight_mutate_rate      = 0.8
weight_replace_rate     = 0.1

[DefaultSpeciesSet]
compatibility_threshold = 3.0

[DefaultStagnation]
species_fitness_func = max
max_stagnation       = 20
species_elitism      = 2

[DefaultReproduction]
elitism            = 2
survival_threshold = 0.2
```

---

## 📄 Requirements

Contents of `requirements.txt`:

```
neat-python==0.92
pygame==2.5.0
```

---

## 🙌 Credits

- Game based on the original Flappy Bird.
- AI powered by the [neat-python](https://github.com/CodeReclaimers/neat-python) library.
