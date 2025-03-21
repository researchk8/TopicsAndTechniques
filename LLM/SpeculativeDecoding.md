# Speculation
Medusa is a simple framework that democratizes the acceleration techniques for LLM generation with multiple decoding heads.

Speculative decoding, assisted generation, Medusa, and others are a few different names for the same idea. The idea is to generate tokens before the large model actually runs, and only check if those tokens where valid.

So you are making more computations on your LLM, but if you are correct you produce 1, 2, 3 etc.. tokens on a single LLM pass. Since LLMs are usually memory bound (and not compute bound), provided your guesses are correct enough, this is a 2-3x faster inference (It can be much more for code oriented tasks for instance).

Text-generation inference supports 2 main speculative methods:

- Medusa
- N-gram


## Medusa
Medusa is a simple method to create many tokens in a single pass using fine-tuned LM heads in addition to your existing models.

### Research
- https://arxiv.org/abs/2401.10774
- https://www.ijcai.org/proceedings/2018/866

### Tools
- https://github.com/FasterDecoding/Medusa (Medusa: Simple Framework for Accelerating LLM Generation with Multiple Decoding Heads )


## N-gram
N-gram works by trying to find matching tokens in the previous sequence, and use those as speculation for generating new tokens. 

# Resources
- https://huggingface.co/docs/text-generation-inference/en/conceptual/speculation