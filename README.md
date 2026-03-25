# UnityMARL 🎮🤖

[![Python 3.10](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.5-orange.svg)](https://pytorch.org/)
[![XuanCe](https://img.shields.io/badge/XuanCe-1.2.3-green.svg)](https://github.com/agi-brain/xuance)
[![ML-Agents](https://img.shields.io/badge/ML--Agents-1.1.0-red.svg)](https://github.com/Unity-Technologies/ml-agents)

[![中文](https://img.shields.io/badge/中文-README-blue.svg)](./README_CN.md)

> Multi-Agent Reinforcement Learning (MARL) Training Framework based on Unity ML-Agents

This project wraps Unity environments as Python interfaces, integrated with the [XuanCe](https://github.com/agi-brain/xuance) deep reinforcement learning library, to implement training and evaluation of multi-agent reinforcement learning algorithms.

---

## 🚀 Quick Start

### 1. Environment Setup

```bash
# Create and activate conda environment
conda env create -f environment.yml
conda activate unity_xuance
```

### 2. Unity Environment Testing

**macOS (Apple Silicon):**
```bash
# AEC interface test
python unity_wrapper/aec_env_test.py

# Parallel interface test
python unity_wrapper/parallel_env_test.py
```

**Windows:**
```bash
# AEC interface test
python unity_wrapper/aec_env_test.py

# Parallel interface test
python unity_wrapper/parallel_env_test.py
```

### 3. Run XuanCe Training Examples

```bash
cd xuance_toturial/usage
python usage_main.py --env-id CartPole-v1 --parallels 4
```

---

## 🔧 Usage Guide

### macOS Setup

1. Place your Unity-built `.app` (e.g., `combat.app`) in the project root directory
2. Modify the path in `unity_wrapper/*.py`:
   ```python
   engine_configuration_channel = EngineConfigurationChannel()
   env_path = "combat.app"  # macOS executable path
   ```
3. Run test scripts to verify the environment interface

### Windows Setup

1. Build your Unity environment as a Windows executable (`.exe` folder)
2. Place the `.exe` and its associated `_Data` folder in the project root directory
3. Modify the path in `unity_wrapper/*.py`:
   ```python
   engine_configuration_channel = EngineConfigurationChannel()
   env_path = "combat.exe"  # Windows executable path
   ```
4. Run test scripts to verify the environment interface:
   ```bash
   python unity_wrapper/aec_env_test.py
   ```

### Unity Environment Wrapper

The project uses `mlagents-envs` to wrap Unity environments into standard [PettingZoo](https://pettingzoo.farama.org/) interfaces:

- **AEC Interface** (`UnityAECEnv`): Sequential multi-agent interaction
- **Parallel Interface** (`UnityParallelEnv`): Parallel multi-agent interaction

### RL Training

XuanCe library supports various algorithms:

- **Single-Agent**: PPO, A2C, DQN, DDPG, SAC, TD3, etc.
- **Multi-Agent**: MAPPO, QMIX, VDN, MADDPG, etc.

---

## 📦 Core Dependencies

| Package       | Version   | Purpose                    |
| ------------- | --------- | -------------------------- |
| Python        | 3.10      | Programming Language       |
| PyTorch       | 2.5.1     | Deep Learning Framework    |
| XuanCe        | 1.2.3     | RL Algorithm Library       |
| mlagents-envs | 1.1.0     | Unity Environment Interface|
| Gym/Gymnasium | 0.26/0.28 | Standard RL Environment API|
| PettingZoo    | 1.24.3    | Multi-Agent Environment API|

---

## 📚 References

- [Unity ML-Agents Documentation](https://unity-technologies.github.io/ml-agents/)
- [XuanCe Documentation](https://xuance.readthedocs.io/)
- [PettingZoo Documentation](https://pettingzoo.farama.org/)

---

## 📄 License

MIT License

---

*Made with ❤️ for Multi-Agent Reinforcement Learning*
