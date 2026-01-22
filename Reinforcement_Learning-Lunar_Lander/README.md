# Reinforcement Learning - Lunar Lander

This notebook implements Proximal Policy Optimization (PPO) to train an agent to land a spacecraft safely on a landing pad in the Lunar Lander 2D environment.

- **Notebook**: `Reinforcement_Learning-Lunar_Lander.ipynb`
- **Goal**: Train a PPO agent to successfully land the lunar lander using actor-critic methods with Generalized Advantage Estimation (GAE).

## What it's about

- **PPO Algorithm**: Implement Proximal Policy Optimization from scratch.
- **Actor-Critic Architecture**: Separate networks for policy (actor) and value function (critic).
- **GAE**: Use Generalized Advantage Estimation for stable advantage computation.
- **Lunar Lander Environment**: Gymnasium's `LunarLander-v3` environment with continuous control.

## How to run

1. Open the notebook: `Reinforcement_Learning-Lunar_Lander.ipynb`
2. Install dependencies (see below).
3. Run cells sequentially. The notebook includes:
   - Environment setup
   - Actor and Critic network definitions
   - PPO training loop with GAE
   - Visualization of training progress
   - Episode reward and length plots
   - Loss curves for actor and critic

## Dependencies

- Python 3.9+
- PyTorch
- Gymnasium (with Box2D)
- matplotlib, numpy
- swig (for Box2D physics engine)
- Jupyter

Install:
```bash
pip install torch gymnasium[box2d] matplotlib numpy swig jupyter
```

## What we're trying to achieve

- **Learn Safe Landing**: Train an agent to navigate and land the spacecraft on the landing pad.
- **Stable Policy Learning**: Use PPO's clipped objective to prevent large policy updates.
- **Efficient Exploration**: Balance exploration vs exploitation using entropy regularization.

## Key Components

- **KL Divergence Analysis**: Understand KL divergence properties for multivariate Gaussians (used in policy updates).
- **PPO Implementation**: Full PPO algorithm with:
  - Rollout collection
  - GAE computation
  - Clipped surrogate objective
  - Value function learning
- **Visualization**: Training curves showing reward improvement, episode lengths, and loss convergence.

## Expected Results

- Episode rewards should increase over training (from negative to positive values).
- Episode lengths should stabilize as the agent learns efficient landing strategies.
- Actor and critic losses should converge as the policy improves.

