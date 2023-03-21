1.import change
"""
import gym
"""

"""
import gymnasium as gym
"""

2. Reset Environment
"""
observation = env.reset(seed=42)
"""

"""
observation,info = env.reset(seed=42)
"""

3. Environement Step
"""
observation, reward,done, info = env.step(action)
"""
"""
observation, reward, terminated, truncated, info = env.step(action)
"""
