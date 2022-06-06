# Competition_3v3snakes

## Environment

<!-- ![image](https://github.com/jidiai/Competition_3v3snakes/blob/master/assets/snakesdemo.gif) -->
<img src="https://github.com/jidiai/Competition_3v3snakes/blob/master/assets/snakesdemo.gif" alt="Competition_3v3snakes" width="500" height="250" align="middle" />

### Observation Space

一个字典，字典的键为1至7的正整数和 "board_width"、 "board_height"、 "last_direction"，"controlled_snake_index" 。 其中1表示豆子，2至7表示蛇；字典的中的值为一个以[h,w]坐标为元素的列表，表示豆子的位置或蛇身的位置，其中h表示距左上角原点的垂直距离，w表示距原点的水平宽度；在2至7对应的值当中，列表元素从左至右表示对应蛇的蛇头至蛇尾的位置；"board_width"的值为地图的宽，"board_height" 的值为地图的高，"last_direction"的值为上一步各个蛇的方向，"controlled_snake_index"的值为控制蛇的序号。

### Action Space

长度为n_action_dim的列表，其中n_action_dim=1，可选动作数为4，每个元素为Gym当中的Discrete类（[Discrete Link](https://github.com/openai/gym/blob/master/gym/spaces/discrete.py)），如[[Discrete(4)]]。



## Installation

Requires `Python==3.6`.

We recommend do it in a virtual env.

Take `conda` for example:

```sh
conda create -n snake python=3.6
conda activate snake
```

### Install Packages

Git clong the repo to include all the submodules:

```sh
git clong https://github.com/joenghl/2022RL_Snake.git
```

Then install the packages using `requirements.txt`:

```sh
pip install -r requirements.txt
```

## How to train rl-agent

>python rl_trainer/main.py

By default-parameters, the total reward of training is shown below.

![image](https://github.com/jidiai/Competition_3v3snakes/blob/master/assets/training.png)


You can edit different parameters, for example

>python rl_trainer/main.py --algo "bicnet" --epsilon 0.8

Baseline performance:

You can locally evaluation your model.

>python evaluation_local.py --my_ai rl --opponent random

![image](https://github.com/jidiai/Competition_3v3snakes/blob/master/assets/baseline.png)


---

### How to test submission 

You can locally test your submission. At Jidi platform, we evaluate your submission as same as **run_log.py**

Once you run this file, you can locally check battle logs in the folder named "logs".

For example, 

>python run_log.py --my_ai "random" --opponent "rl"

---

### Ready to submit 

1. Random policy --> **agent/random/submission.py**
2. RL policy --> **all files in agent/rl/**

---

### Watch reply locally

1. Open reply/reply.html in any browser.
2. Load a log.
3. Reply and watch ^0^.
