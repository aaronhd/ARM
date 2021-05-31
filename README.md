# Attention-driven Robotic Manipulation (ARM)

![task grid image missing](readme_files/qattention_heatmap.png)

This codebase is home to:
- Q-attention: Enabling Efficient Learning for Vision-based Robotic Manipulation

## Installation

ARM is trained using the **YARR framework**. Head to the [YARR github](https://github.com/stepjam/YARR) page and follow 
installation instructions.

ARM is evaluated on **RLBench** 1.1.0. Head to the [RLBench github](https://github.com/stepjam/RLBench) page and follow 
installation instructions. 

Now install project requirements:
```bash
pip install -r requirements.txt
```

## Running experiments

Be sure to have RLBench demos saved on your machine before proceeding. To generate demos for a task, go to the 
tools directory in RLBench _(rlbench/tools)_, and run:
```bash
python dataset_generator.py --save_path=/mnt/my/save/dir --tasks=take_lid_off_saucepan --image_size=128,128 \
--renderer=opengl --episodes_per_task=100 --variations=1 --processes=1
```


Experiments are launched via [Hydra](https://hydra.cc/). To start training an agent to accomplish 
**take_lid_off_saucepan** with the default parameters on **gpu 0**, then run:
```bash
python launch.py method=ARM rlbench.task=take_lid_off_saucepan rlbench.demo_path=/mnt/my/save/dir framework.gpu=0
```
