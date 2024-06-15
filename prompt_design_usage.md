## Prompt Design and Usage

Suggested Temperature: 0.5 (*However, according to [this blog](https://eugeneyan.com/writing/prompting/#selecting-a-temperature), lower temp reduces the model intelligence.*)

*The whole process is iterative and involves multiple models for solving mathematical problems professionally.*

- The Main Instruction is designed to guide the AI in solving mathematical problems professionally.
- In these series of processes, we use claude-3-opus-20240229 and gpt-4-turbo-2024-04-09 as main models seperately.
  - After model with main prompt completes its solution, the original question and the solution are passed to the same model but with the evaluation instruction for review.
  - After the review, the evaluation is returned to the main model for further improvement.
  - The process continues iteratively until the solution is accurate and well-explained.
  - The iterate period is set to up to 5 times.
- After the final solution from claude-3-opus-20240229 and gpt-4-turbo-2024-04-09 is obtained, they are passed to gpt-4-turbo-2024-04-09 with different instruction for selecting the best solution among the iterated solutions.
  - The model evaluates the solutions based on calculation, reasoning and logic, and clarity and presentation.
  - The model selects the best solution based on the weighted average of these factors.
