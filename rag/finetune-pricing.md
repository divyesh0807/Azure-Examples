# Azure Open Ai Service Fine Tuning Price Change
We’re updating our billing for fine tuning with the Azure OpenAI Service to bill based on the number of tokens in your training file – instead of the total elapsed training time.






## Model

### Babbage-002 

- Previous Price : $34 / hour 
- New Price : $0.0004/1K tokens 

###  Davinci-002 

- Previous Price : $40 / hour 
- New Price : $0.006/1K tokens 

### GPT-35-Turbo (4k) 

- Previous Price : $45 / hour 
- New Price : $0.008/1K tokens 

### GPT-35-Turbo (16K) 

- Previous Price :$68 / hour 
- New Price : $0.008/1K tokens 

### GPT-4 

- Previous Price : $102 / hour 
- New Price : $0.080/1K tokens 


## reasons for change 

Why make this change? If you’ve fine-tuned before – or thought about it and decided against it – you may have struggled to estimate the cost. While it’s easy to guess relative time (longer files, more epochs take longer) there’s was no easy way to estimate an exact time. Now, it’s simple: count the number of tokens in your file, multiply that by the per token price, and the number of epochs and you’ve got a decent estimate for the overall costs. Note: the raw token count for your file may be higher than the actual token counts you’ll be charged for, so this is an estimate, not the actual value you will be billed.  

 

In practice, this change will be a substantial discount for some training runs. For example, I recently fine-tuned GPT-35-Turbo 0613 with a small (45k token) dataset over 3 epochs. With hourly billing, this job took 1.5 hours and cost me $67.50 -- but with the switch to token based billing, it costs just $1.08! The price difference isn’t quite as big for large files: I trained GPT-35-Turbo 0125 with a large file (2.2M tokens) for one epoch, taking 1 hour and 15 minutes, at a price of $85 when billed hourly – or ~$18 when based on tokens. 


Not sure how to count up the tokens in your file? Tools like OpenAI's tiktoken library make it super simple to specify your model and write a short script to count tokens in your training data. Alternatively, many IDEs support plug-ins to provide token counts right in your status bar.  

 

With these updates, experimenting with fine tuning should be easier than ever: you can easily estimate costs, and with lower and more transparent pricing you can train more models. More training runs allows you to assess the impact of different parameter combinations, data sets and more – and hopefully, create the best custom models for your use case. 