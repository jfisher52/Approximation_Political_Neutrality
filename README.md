# Political Neutrality in AI is Impossible — But Here’s How To Approximate It
This repository contains the code and the scripts to reproduce the experiments from the paper
[Political Neutrality in AI is Impossible — But Here’s How To Approximate It](). 

In this position paper we argue that true political neutrality is neither feasible nor universally desirable due to its subjective nature and the biases inherent in AI training data, algorithms, and user interactions. However, inspired by Joseph Raz's philosophical insight that "neutrality [...] can be a matter of degree" (Raz, 1986), we argue that striving for some neutrality remains essential for promoting balanced AI interactions and mitigating user manipulation. Therefore, we use the term "approximation" of political neutrality to shift the focus from unattainable absolutes to achievable, practical proxies. We propose eight techniques for approximating neutrality across three levels of conceptualizing AI, examining their trade-offs and implementation strategies. In addition, we explore two practical applications of these approximations to illustrate their practicality. Finally, we assess our framework on current large language models (LLMs) at the output level, providing a demonstration of how it can be evaluated. This work seeks to advance nuanced discussions of political neutrality in AI and promote the development of responsible, aligned language models.

In this repo, we provide code which implements the experimentation which explores how current models utilize our approximation of political neutrality in the output-level

Raz, J. \textit{The Morality of Freedom}. Oxford University Press, Oxford, GB, 1986.

## Dependencies
The code is written in Python and the dependencies are:
- Python >= 3.10.13
- Pandas

## Datasets Creation
We created a new dataset composed of seven datasets types which all take form of input-label pairs, where the input is a user-query, and the label is the approximation technique (see the paper for more details on data collection). The raw data for each of the seven datasets is under `Data/data...`. However, we processed the raw data to formulate questions, regardless of the original data type. The file `create_test_dataset.py` was used to process the raw data into prompts for model generation. The final prompt file can be found [here](). 

After the prompt creation, we generated responses from ten models: GPT-4o\cite, GPT-4o-Mini, Gemini-1.5 Flash, Gemini-1.5 Pro, Claude-3.5 Sonnet, Llama-3.3 (70B) with 4bit quantization, OLMO-2 (13B) with bfloat16, R1-Distill-Llama (70B), and Qwen2.5 (72B) Instruct. The final dataset, with all generations, can be downloaded from [here](). 

## Generation Annotation
Model generations were then labelled as one of the four approximation techniques ("refusals", "avoidance", "reasonable pluralism", or "output transparency"), or either "no approximation" if not approximation was used, or "bias" if the responses took a side but did not fall under ``output transparency''. The model generations were annotated with the corresponding approximation techniques using GPT-4o using prompting. To create the annotation prompts for GPT-4o, we used the file `create_annotate_prompts.py`. The final annotations can be found [here]()


## Citation
If you find this repository useful, or you use it in your research, please cite:
```

```
    
## Acknowledgements

