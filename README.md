# Should You Jev?

English | [日本語](README.ja.md)

A decision flow for choosing a model or processing method based on the characteristics of the input data.

```mermaid
flowchart TD
    A{"No intelligence<br/>needed?"}
    B{"Real-time?"}
    C{"High volume?"}
    D{"Is the input<br/>unstructured data?"}
    E{"Are categories dynamic?<br/>Can't prepare<br/>training data?"}
    F{"Training too much work?"}

    J["Jev"]
    BERT["BERT"]
    IF["if statement"]
    LIGHT["Lightweight LLM"]
    SOME["Moderately capable LLM"]

    A -->|Yes| B
    A -->|No| SOME
    B -->|Yes| C
    B -->|No| LIGHT
    C -->|Yes| D
    C -->|No| LIGHT
    D -->|Yes| E
    D -->|No| IF
    E -->|Yes| F
    E -->|No| BERT
    F -->|Yes| J
    F -->|No| BERT
```

## Decision flow

- If intelligence is not required, use a moderately capable LLM.
- If real-time processing is required, check the data volume.
- For high-volume, unstructured data with dynamic categories—or when training data cannot be prepared—consider the training effort.
- If training is too much work, use Jev; otherwise, use BERT.
- Use an `if` statement for structured data, or a lightweight LLM when real-time processing is not required.
