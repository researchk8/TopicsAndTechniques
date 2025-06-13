# LLM

## LLM Settings

### Temperature

In short, the lower the temperature the more deterministic the results in the sense that the highest probable next token
is always picked. Increasing the temperature could lead to more randomness encouraging more diverse or creative outputs.
We are essentially increasing the weights of the other possible tokens. In terms of application, we might want to use a
lower temperature for something like fact-based QA to encourage more factual and concise responses. For poem generation
or other creative tasks, it might be beneficial to increase the temperature.

### Top_p

Similarly, with top_p, a sampling technique with temperature called nucleus sampling, you can control how deterministic
the model is at generating a response. If you are looking for exact and factual answers keep this low. If you are
looking for more diverse responses, increase to a higher value.