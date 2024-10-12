# Multimodal Integrity Check

**Multimodal Integrity Check** is a methodology designed to verify that multimodal Generative AI (GenAI) models, such as LLaVA, effectively integrate all data types they receive (e.g., text prompts, RAG data, and image data). This project aims to identify when models compensate for missing modalities by relying too heavily on the remaining inputs—resulting in hallucination.

## Problem Statement
GenAI models are widely known as **pathological liars**, a behavior commonly referred to as **hallucination** in the AI community. This means that they can generate plausible but incorrect or fabricated responses, even when critical input data is missing. For example, a model might hallucinate visual elements when no image data is provided, generating a coherent yet false description based solely on text or RAG (retrieval-augmented generation) data.

## Example Case: Jenkins Data Integrity Check
In this project, we demonstrate this methodology using an example case that includes:
- **Jenkins Image**: An image of the Jenkins character.
- **RAG Data**: Text describing imaginary facts about Jenkins, used as background information.
- **Text Prompt**: A question asking about the character in the image, without explicitly referring to any contextual details provided by the RAG data or image.

This example helps verify whether the model uses all inputs effectively or hallucinates missing details, providing a means to ensure the model's multimodal functionality is sound.

## How It Works

1. **Controlled Input Tests**:
   - The model is tested with various combinations of inputs (e.g., text + RAG + image, or text + RAG without image) to observe whether the model adjusts its response based on the data available.
   - We track whether the model outputs plausible answers even when an input type (e.g., image) is missing, indicating hallucination.

2. **Sanity Check Prompts**:
   - Carefully constructed prompts are provided that should depend on a specific data type. If the model compensates for missing data by relying on other inputs, we detect this behavior as hallucination.

3. **Comparison of Responses**:
   - Outputs are compared across different input configurations to assess if the model over-relies on certain modalities or if it produces consistent results only when all input types are provided.

## Key Features
- **Data Flow Control**: Easily toggle between feeding all or partial data types to the model.
- **Multimodal Sanity Checks**: Detect and highlight instances where the model compensates for missing modalities with fabricated responses.
- **Customizable**: Adapt the tool for any multimodal GenAI model (e.g., LLaVA, GPT-4 with vision, etc.).

## Why Use Multimodal Integrity Check?
- **Prevent Hallucination**: Ensure the model only uses the inputs provided, without generating content based on incomplete data.
- **Improve Model Reliability**: Guarantee that your multimodal GenAI models correctly process and integrate all available input types.
- **Debugging Support**: Helps developers pinpoint issues related to multimodal data processing, enabling them to improve the performance and reliability of their models.

## About the Project
This methodology was initially developed as part of the **Concept Discovery** project, where a case involving Jenkins was used to illustrate the potential for hallucination in multimodal AI. By moving this case to **Multimodal Integrity Check**, we aim to provide a standalone tool for detecting and mitigating these issues in any multimodal AI application.
