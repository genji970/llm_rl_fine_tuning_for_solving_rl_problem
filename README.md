Not yet done.

1) using normal actor network and critic network, gain trajectory. This part aims to gain failed data which means overfitting/not properly learn.

2) With thses data, fine tune meta llama with lora method.Other parameters , require_grad = False

3) llm must output action , q_value. Input is state.


 transformer architecture is mainly based on distribution of weights. hallucination occur due to lack of generalization to real world. Because of these reasons, transformer has limit. 

 I think roll out is the one way to solve this limit. But 100% randomness is bad, so I choose rl method. And whatsmore, if I add indicator to prompt, it will work better.

e.g)
 prompt : "This sequence is not that good/This sequence is less likely to gain higher reward. + f"state : {state}"

 Also, I think f(reward_1 ~ reward_n) > f(reward) will be much better. Meaning, putting more thatn two sequences is better than just putting one state sequence  
