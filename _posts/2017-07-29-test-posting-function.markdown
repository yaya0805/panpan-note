---
layout: post
title:  "Test posting function~"
date:   2017-07-29 23:37:55 +0800
categories: jekyll update
---
New post in `_posts` dir.
```python
def main():
#    for d in ['/gpu:2', '/cpu:0']:
#        with tf.device(d):
    print ("====== Build Agent ======")
    agent = Agent(num_actions=4)

    if TRAIN:  # Train mode
        print ("====== Train Mode ======")
        print ("====== Build Monitor ======")
        env = Monitor(observation_dim=90*160*3, monitor_batch_size=1, is_training=True)
        for _ in range(NUM_EPISODES):
            terminal = False
            observation = env.reset()
            #for _ in range(random.randint(1, NO_OP_STEPS)):
                #last_observation = observation
                #observation, _, _ = env.step(0)  # Do nothing
            last_observation = observation
            state = agent.get_initial_state(observation, last_observation)
            print ("====== Start training ======")
            while not terminal:
                #print 'Start'
                last_observation = observation
                action = agent.get_action(state)
                observation, reward, terminal = env.step(action)
                # env.render()
                processed_observation = preprocess(observation, last_observation)
#                with tf.device('/gpu:2'):
                state = agent.run(state, action, reward, terminal, processed_observation)
```
