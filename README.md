# Reinforcement-Learning
Creating Frozen Lake Environment using python

#implementing FrozenLakeEnvironment
import gymnasium as gym
import time
env=gym.make('FrozenLake-v1',render_mode='human')
env.reset()
env.render()
time.sleep(2)
#print(env.observation_space)
#print(env.action_space)
#print(env.p[6][3])
#print(env.step(2))
print("Time step: 0 before moving")
eps=20
t_s=20
for i in range(eps):
    env.reset()
    time.sleep(2)
    print("Time Step: 0")
    env.render()
    print("Eposide: ",i+1)
    for t in range(t_s):
        random_action=env.action_space.sample()
        next_state,reward,done,info,trans_prob=env.step(random_action)
        print("Time step is {}".format(t+1))
        env.render()
        time.sleep(2)
        if done:
            break
