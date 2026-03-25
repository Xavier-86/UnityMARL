# UnityMARL 🎮🤖

[![Python 3.10](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.5-orange.svg)](https://pytorch.org/)
[![XuanCe](https://img.shields.io/badge/XuanCe-1.2.3-green.svg)](https://github.com/agi-brain/xuance)
[![ML-Agents](https://img.shields.io/badge/ML--Agents-1.1.0-red.svg)](https://github.com/Unity-Technologies/ml-agents)

> 基于 Unity ML-Agents 的多智能体强化学习 (MARL) 训练框架

本项目将 Unity 环境封装为 Python 接口，结合 [XuanCe](https://github.com/agi-brain/xuance) 深度强化学习库，实现多智能体强化学习算法的训练与评估。

---

## 📁 项目结构

```
UnityMARL/
├── 📂 combat.app              # Unity 可执行环境 (macOS Apple Silicon)
├── 📂 unity_wrapper/          # Unity 环境 Python 封装
│   ├── aec_env_test.py        # AEC (Agent-Environment Cycle) 接口示例
│   └── parallel_env_test.py   # Parallel 并行环境接口示例
├── 📂 xuance_toturial/        # XuanCe 强化学习教程
│   ├── usage/                 # 基础使用示例
│   ├── create_env/            # 自定义单智能体环境
│   ├── create_ma_env/         # 自定义多智能体环境
│   ├── args_sarl_example.py   # 单智能体 RL 示例
│   └── marl_example.py        # 多智能体 RL 示例
├── 📂 libs/                   # 本地依赖库
│   └── xuance/                # XuanCe 源码 (自定义修改)
├── 📂 logs/                   # 训练日志输出
├── environment.yml            # Conda 环境配置
└── README.md                  # 本文件
```

---

## 🚀 快速开始

### 1. 环境配置

```bash
# 创建并激活 conda 环境
conda env create -f environment.yml
conda activate unity_xuance
```

### 2. 运行 Unity 环境测试

```bash
# AEC 接口测试
python unity_wrapper/aec_env_test.py

# Parallel 接口测试
python unity_wrapper/parallel_env_test.py
```

### 3. 运行 XuanCe 训练示例

```bash
cd xuance_toturial/usage
python usage_main.py --env-id CartPole-v1 --parallels 4
```

---

## 📦 核心依赖

| 包名 | 版本 | 用途 |
|------|------|------|
| Python | 3.10 | 编程语言 |
| PyTorch | 2.5.1 | 深度学习框架 |
| XuanCe | 1.2.3 | 强化学习算法库 |
| mlagents-envs | 1.1.0 | Unity 环境交互 |
| Gym/Gymnasium | 0.26/0.28 | 标准 RL 环境接口 |
| PettingZoo | 1.24.3 | 多智能体环境接口 |

---

## 🔧 使用说明

### Unity 环境封装

项目使用 `mlagents-envs` 将 Unity 环境封装为标准的 [PettingZoo](https://pettingzoo.farama.org/) 接口：

- **AEC 接口** (`UnityAECEnv`): 顺序执行多智能体交互
- **Parallel 接口** (`UnityParallelEnv`): 并行执行多智能体交互

### 强化学习训练

使用 XuanCe 库支持多种算法：

- **单智能体**: PPO、A2C、DQN、DDPG、SAC、TD3 等
- **多智能体**: MAPPO、QMIX、VDN、MADDPG 等

---

## 📝 自定义 Unity 环境

1. 在 Unity 中构建你的环境
2. 将 `.app` (macOS) 或 `.exe` (Windows) 放入项目根目录
3. 修改 `unity_wrapper/*.py` 中的路径配置
4. 运行测试脚本验证环境接口

---

## 📚 相关链接

- [Unity ML-Agents 文档](https://unity-technologies.github.io/ml-agents/)
- [XuanCe 文档](https://xuance.readthedocs.io/)
- [PettingZoo 文档](https://pettingzoo.farama.org/)

---

## 📄 License

MIT License

---

*Made with ❤️ for Multi-Agent Reinforcement Learning*
