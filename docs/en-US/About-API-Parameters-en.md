This repository's prompt examples use the RWKV-5-7B-World model. With adjustments in model versions and parameters, the generated results may vary.

You can alter the generation effects of the example prompts by adjusting the API parameters.

## API Parameter Introduction

The main API parameters and their effects are as follows:

| Parameter  | Effect |
| ---  | --- |
| Temperature | Sampling temperature, like giving the model a drink. A higher value increases randomness and creativity, while a lower value makes it more conservative and stable. |
| Top_P | Like giving the model a sedative. It prioritizes results within the top n% probability mass. Setting it to 0.1 considers the top 10%, yielding higher-quality but more conservative results. Setting it to 1 considers all results, lowering quality but increasing diversity. |
| Presence Penalty | Positive values penalize tokens based on whether they have appeared in the text so far, increasing the model's likelihood of addressing new topics. |
| Frequency Penalty | Positive values penalize tokens based on their frequency in the text so far, reducing the likelihood of the model repeating the same sentences verbatim. |

Among these parameters, Temperature and Top_P have the most significant impact on the generation results.

## Recommended parameter configurations

Recommended parameter configurations are provided for different tasks:

**For writing novels and dialogues**, where the model needs to attempt various parameter combinations, consider the following:

- Temperature 1.2, Top_P 0.5
- Temperature 1.4, Top_P 0.4
- Temperature 1.4, Top_P 0.3
- Temperature 1.4, Top_P 0.2

**For relatively mechanical tasks** such as material-based questions, article summaries, etc., you can set the parameters as:

- Temperature 1, Top_P 0.2
- Temperature 1, Top_P 0.1
- Temperature 1, Top_P 0

For instance, if you're performing a task like keyword extraction, which doesn't require the model to engage in any open-ended thinking, you can set Temperature to 1 and Top_P, Presence Penalty, and Frequency Penalty all to 0.