# AI Models

## Components

- PARAMETER: parameters for run the model.
- TEMPLATE: The full prompt template to be sent to the model.
- SYSTEM: Specifies the system message that will be set in the template.
- ADAPTER: Defines the (Q)LoRA adapters to apply to the model.
- MESSAGE: Specify message history.

## Model

### arch

### parameters

### quantization

### a lot more

## Params

### mirostat

Enable Mirostat sampling for controlling perplexity. (default: 0, 0 = disabled, 1 = Mirostat, 2 = Mirostat 2.0)

### mirostat_eta

Influences how quickly the algorithm responds to feedback from the generated text. A lower learning rate will result in
slower adjustments, while a higher learning rate will make the algorithm more responsive. (Default: 0.1)    float
mirostat_eta 0.1

### mirostat_tau

Controls the balance between coherence and diversity of the output. A lower value will result in more focused and
coherent text. (Default: 5.0)    float mirostat_tau 5.0

### num_ctx

Sets the size of the context window used to generate the next token. (Default: 2048)    int num_ctx 4096

### repeat_last_n

Sets how far back for the model to look back to prevent repetition. (Default: 64, 0 = disabled, -1 = num_ctx)

### repeat_penalty

Sets how strongly to penalize repetitions. A higher value (e.g., 1.5) will penalize repetitions more strongly, while a
lower value (e.g., 0.9) will be more lenient. (Default: 1.1)

### temperature

The temperature of the model. Increasing the temperature will make the model answer more creatively. (Default: 0.8)

### seed

Sets the random number seed to use for generation. Setting this to a specific number will make the model generate the
same text for the same prompt. (Default: 0)

### stop

Sets the stop sequences to use. When this pattern is encountered the LLM will stop generating text and return. Multiple
stop patterns may be set by specifying multiple separate stop parameters in a modelfile.

### num_predict

Maximum number of tokens to predict when generating text. (Default: -1, infinite generation)

### top_k

Reduces the probability of generating nonsense. A higher value (e.g. 100) will give more diverse answers, while a lower
value (e.g. 10) will be more conservative. (Default: 40)

### top_p

Works together with top-k. A higher value (e.g., 0.95) will lead to more diverse text, while a lower value (e.g., 0.5)
will generate more focused and conservative text. (Default: 0.9)

### min_p

Alternative to the top_p, and aims to ensure a balance of quality and variety. The parameter p represents the minimum
probability for a token to be considered, relative to the probability of the most likely token. For example, with p=0.05
and the most likely token having a probability of 0.9, logits with a value less than 0.045 are filtered out. (Default:
0.0)

## System

The SYSTEM instruction specifies the system message to be used in the template, if applicable.

    SYSTEM """<system message>"""

## Template
TEMPLATE of the full prompt template to be passed into the model. It may include (optionally) a system message, a user's message and the response from the model.

| Variable          | 	Description                                                                                  |
|-------------------|-----------------------------------------------------------------------------------------------|
| {{ .System }}     | 	The system message used to specify custom behavior.                                          |
| {{ .Prompt }} 	 | The user prompt message.                                                                      |
| {{ .Response }} 	 | The response from the model. When generating a response, text after this variable is omitted. |


Sample:

    TEMPLATE """{{ if .System }}<|im_start|>system
    {{ .System }}<|im_end|>
    {{ end }}{{ if .Prompt }}<|im_start|>user
    {{ .Prompt }}<|im_end|>
    {{ end }}<|im_start|>assistant
    """

## Adapter

The ADAPTER instruction specifies a fine tuned LoRA adapter that should apply to the base model. The value of the adapter should be an absolute path or a path relative to the Modelfile. The base model should be specified with a FROM instruction. If the base model is not the same as the base model that the adapter was tuned from the behaviour will be erratic.

    ADAPTER <path to safetensor adapter>


## LICENSE

The LICENSE instruction allows you to specify the legal license under which the model used with this Modelfile is shared or distributed.

    LICENSE """
    <license text>
    """

## MESSAGE

The MESSAGE instruction allows you to specify a message history for the model to use when responding. Use multiple iterations of the MESSAGE command to build up a conversation which will guide the model to answer in a similar way.

    MESSAGE <role> <message>

Valid roles 

| Role      | 	Description                                                  |
|-----------|---------------------------------------------------------------|
| system    | 	Alternate way of providing the SYSTEM message for the model. |
| user      | An example message of what the user could have asked.         |
| assistant | 	An example message of how the model should respond.          |


Example conversation

    MESSAGE user Is Toronto in Canada?
    MESSAGE assistant yes
    MESSAGE user Is Sacramento in Canada?
    MESSAGE assistant no
    MESSAGE user Is Ontario in Canada?
    MESSAGE assistant yes



# Resources

- https://github.com/ollama/ollama/blob/main/docs/modelfile.md