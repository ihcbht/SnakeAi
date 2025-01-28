# Snake Game AI with Deep Q-Learning

This repository contains the implementation of a Snake Game AI using **Deep Q-Learning**. The project involves building an agent capable of playing the Snake Game autonomously using reinforcement learning techniques like experience replay, target networks, and epsilon-greedy exploration.

---

## Features

1. **AI-Controlled Snake Game**:
   - Agent learns through Deep Q-Learning to play Snake Game efficiently.
   - Implements strategies to navigate, collect food, and avoid collisions.
   
2. **Neural Network Integration**:
   - PyTorch-based neural network for Q-value approximation.
   - Utilizes feed-forward layers with ReLU activation.

3. **Training and Optimization**:
   - Utilizes experience replay and Bellman Equation for stable learning.
   - Includes exploration vs. exploitation techniques using epsilon-greedy policy.

4. **Performance Visualization**:
   - Tracks scores and mean scores with real-time graph plotting using Matplotlib.

---

## Project Structure

```
.
├── game.py                # Contains the SnakeGame and SnakeGameAI classes
├── agent.py               # Defines the Agent class responsible for training
├── model.py               # Implementation of the Q-Network and Trainer
├── helper.py              # Utility to plot training progress
├── README.md              # This documentation
```

---

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/snake-game-ai.git
   cd snake-game-ai
   ```

2. Set up the environment:
   ```bash
   conda create -n snake_ai python=3.7
   conda activate snake_ai
   ```

3. Install required libraries:
   ```bash
   pip install pygame torch matplotlib ipython
   ```

---

## How to Run

### 1. Human-Playable Game:
Run the following to play the game manually using arrow keys:
```bash
python game.py
```

### 2. AI-Controlled Game:
Train and watch the AI agent:
```bash
python agent.py
```

### 3. View Training Progress:
Real-time training progress is plotted with scores and average scores using Matplotlib.

---

## Code Explanation

### `game.py`
- Implements the Snake Game using `pygame`.
- Two classes:
  - `SnakeGame`: Human-playable game.
  - `SnakeGameAI`: Adapted for AI training with a reward system.

### `agent.py`
- The **Agent** class coordinates the game and the model:
  - Gets the current state of the game.
  - Chooses actions using epsilon-greedy strategy.
  - Stores experience for replay.
  - Trains the Q-Network using short and long memory.

### `model.py`
- Implements the **Linear_QNet** for Q-value approximation.
- Includes a **QTrainer** class for training the model using Bellman Equation.

### `helper.py`
- Plots the game score and mean score during training for performance monitoring.

---

## Core Concepts

1. **Reinforcement Learning**:
   - Reward system: +10 for eating food, -10 for collisions, 0 for every other move.
   - Exploration (random moves) vs. Exploitation (based on learned policy).

2. **Deep Q-Learning**:
   - Uses a feed-forward neural network to approximate Q-values.
   - Updates Q-values using:
     ```
     Q_new = Reward + γ * max(Q(next_state))
     ```

3. **Training Process**:
   - Collects states, actions, rewards, and next states.
   - Uses experience replay for stable and efficient learning.
   - Regularly updates the target network for consistent predictions.

---

## Results

- **Training Stats**:
  - Total games played: 254
  - Highest score: 73
  - Average score: 20.28

- **Visual Performance**:
  - Dynamic graph plotting of scores and average scores.

---

## Future Scope

- Implement advanced neural network architectures like CNNs for feature extraction.
- Explore multi-agent reinforcement learning for competitive Snake gameplay.
- Adapt this system for real-world applications like robotic pathfinding and resource optimization.

---

## References

1. [PyTorch Documentation](https://pytorch.org/docs/stable/index.html)
2. [Pygame Documentation](https://www.pygame.org/docs/)
3. [Deep Q-Learning Algorithm](https://huggingface.co/learn/deep-rl-course/en/unit3/deep-q-algorithm)

---

## License

This project is licensed under the [MIT License](LICENSE).
