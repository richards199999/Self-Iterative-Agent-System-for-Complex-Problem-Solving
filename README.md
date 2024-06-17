# Self-Iterative Agent System for Complex Problem Solving

---

Link to the CN version: [Here](https://github.com/richards199999/Agent-System-for-Complex-Promblem-Solving/blob/main/README_CN.md)

---

This was also my solution for the [Alibaba Mathematical Competition (AI Challenge)](https://damo.alibaba.com/alibaba-global-mathematics-competition). I was surprised that it was so simple yet achieved such good results compared to others who used complex multi-agent systems.

Let me share my general thoughts:

I let multiple LLMs engage in multi-round "self-questioning" to seek the optimal solution, borrowing from the idea of debate, iteratively refining the current problem-solving process, and finally selecting the optimal solution to give a conclusion.

This system contains two sets of models: the main model/student model and the evaluation model/teacher model. The overall process is roughly as follows:

![image](https://github.com/richards199999/Agent-System-for-Complex-Promblem-Solving/assets/142148415/3d946ec6-8433-4da2-9789-7281b0831873)

1. The main model (such as GPT-4 Turbo or Claude-3 Opus) answers math problems step by step according to detailed instructions:
   - List relevant knowledge points
   - Write down initial thought process
   - Expand on the specific calculation process (without skipping steps)
   - Give the final result
2. The main model's answer is submitted to the evaluation model for review. The evaluation model also proceeds step by step:
   - Overview to check for obvious loopholes and give initial feedback
   - Carefully check the calculation process to find possible errors
   - Evaluate whether the reasoning logic is rigorous
   - Summarize all feedback
3. The evaluation model's feedback is returned to the main model for reference to revise the answer.
4. Repeat the above process iteratively several times (such as 5 times) to continuously improve the answer.
5. Iterate using two sets of models separately to finally obtain two revised answers.
6. Use GPT-4 Turbo to score and compare the two answers in terms of calculation, logic, clarity, etc., and provide the best answer.

For extra details, please check [my blog](https://blog.richardstu.com/solution-sharing-and-some-thoughts-about-alibaba-mathematical-competition-for-ai)!
