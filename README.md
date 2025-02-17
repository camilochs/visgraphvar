# VisGraphVar: A Benchmark Generator for Assessing Variability in Graph Analysis Using Large Vision-Language Models
This research introduces VisGraphVar, a benchmark generator that evaluates Large Vision-Language Models' (LVLMs) capabilities across seven graph-related visual tasks. Testing of six LVLMs using 990 generated graph images reveals significant performance variations based on visual attributes and imperfections, highlighting current limitations compared to human analysis. The findings emphasize the need for comprehensive testing beyond reasoning tasks and guide development of more robust visual analysis systems.

Home page: [here](https://camilochs.github.io/visgraphvar-website/).

## Research Findings

Our research, detailed in the paper ["VisGraphVar: A Benchmark Generator for Assessing Variability in Graph Analysis Using Large Vision-Language Models"]([https://arxiv.org/abs/2411.14832](https://ieeexplore.ieee.org/document/10855899)), demonstrates the effectiveness of this approach. 

## Installation

Clone this repository and install the required dependencies:
```
git clone git@github.com:camilochs/visgraphvar.git
cd visgraphvar
pip3 -r requirements.txt
```

## VisGraphVar Dataset

To review the dataset generated with VisGraphVar in the paper you can find it in [Huggingface](https://huggingface.co/datasets/camilocs/VisGraphVar).

## Create a new benchmark

### Usage

To generate a benchmark of visual graphs you must run the specify module task. The configuration for each task is in `config.yaml`.
```
>> cat visgraphvar/detection/config.yaml
>> python3.11 -m visgraphvar.detection.main  
```

Folders with images are generated inside the task folder.


## Evaluation of a dataset generated by VisGraphVar

- The images generated by each task (folder `visgraphvar/`), that would be the `bechmark_path` in `evaluator/config.yaml`.
- The evaluator is in the `evaluator/` folder.  
- Check the configuration in `evaluator/config.yaml`.
- In the `evaluator/utils/config.yaml` folder you must add the OpenRouter API.

### Usage

In the `evaluator/main.py` file you can choose which task to run. The results for each LVLM should be in the `evaluations` folder inside each `evaluator` task. For example, the result for task 1 (detection), will be found in `evaluator/tasks/detection/evaluations/`.

To execute:
```
>> python3.11 -m evaluator.main
```


## Supplementary Material

All the results of the experiments presented in our paper can be found in the [supplementary material](<supplementary/>) folder.

## Cite
```
@ARTICLE{10855899,
  author={Sartori, Camilo Chacón and Blum, Christian and Bistaffa, Filippo},
  journal={IEEE Access}, 
  title={VisGraphVar: A Benchmark Generator for Assessing Variability in Graph Analysis Using Large Vision-Language Models}, 
  year={2025},
  volume={},
  number={},
  pages={1-1},
  keywords={Visualization;Benchmark testing;Image edge detection;Layout;Cognition;Computational modeling;Generators;Image color analysis;Complexity theory;Image segmentation;benchmark;computer vision;graph theory;large vision-language models},
  doi={10.1109/ACCESS.2025.3535837}
}

```
