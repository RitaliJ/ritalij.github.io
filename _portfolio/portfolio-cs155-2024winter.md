---
title: "Hidden Markov Models for Generation of Shakespeare Sonnets"
excerpt: "(ML) Four dofs robot built and programmed to track balls + other objects<br/><img src='/images/cs155-2024winter-clouds.png'>"
collection: portfolio
---


## Overview

In this project, we explore generative modeling on works of William Shakespeare. In particular, Shakespeare's poems follow a particular English sonnet format with a specific rhyme scheme, syllables constraint, as well as iambic meter. We explore how HMMs and RNNs might be able to capture these complex dependencies within sequences of words and characters. Overall, we notice that the models that we explore in this report start to learn some of the defining elements of Shakespeare's poems, but there is still a large learning curve in terms of capturing complex poetic dependencies as well as semantics and themes of poetry. Along the way, we suggest future model refinements that could help in generating texts more reminiscient of Shakespeare's works.

# Generating Shakespearean Sonnets with Hidden Markov Models and Recurrent Neural Networks

## Overview

This project explores the generation of **Shakespearean-style sonnets** using a **Hidden Markov Model (HMM)**, with extensions for rhyme and structure, and compares its performance to a **character-level LSTM** (Long Short-Term Memory network). The goal was to study classical probabilistic models alongside modern deep learning approaches for natural language generation.

## Project Achievements

- Trained an HMM on Shakespeare’s sonnets and generate structured poetry
- Incorporated **rhyming constraints** and **sonnet formatting** into sampling
- Analyzed the **hidden state dynamics** and **transition matrix**
- Evaluated how training on additional corpora (e.g., modern poetry or prose) influences style and coherence
- Compared quality and creativity against a **character-level LSTM**

## Hidden Markov Model Implementation

- Preprocessed Shakespeare’s corpus by tokenizing into words and sentences
- Trained an HMM with emission and transition probabilities
- Modified sampling to enforce:
  - **14-line sonnet structure**
  - **ABAB CDCD EFEF GG** rhyme scheme using a rhyming dictionary
- Conducted analysis of:
  - Learned **hidden states** and their linguistic patterns
  - The **transition matrix** to understand syntactic flow

### Observations

- Some hidden states specialized in function words, others in verbs or imagery
- The model learned stylistic quirks of Shakespearean English
- Adding prose to the training set diluted poetic rhythm but increased vocabulary diversity

## LSTM Comparison

- Implemented a character-level LSTM trained on the same corpus
- Used temperature-controlled sampling to balance creativity and coherence
- Compared both models qualitatively and quantitatively (e.g., word diversity, meter, rhyme)

### HMM vs LSTM

| Feature | HMM | LSTM |
|--------|------|------|
| Interpretability | ✅ (clear states, transitions) | ❌ (black-box) |
| Structure Control | ✅ (easy to inject rhyme rules) | ⚠️ (requires additional logic) |
| Coherence | ⚠️ (depends on state design) | ✅ (better long-term dependencies) |
| Creativity | ⚠️ (limited variation) | ✅ (richer outputs) |

## Takeaways

- HMMs are surprisingly effective for **controlling structure and interpretability** in generative tasks
- LSTMs offer **more natural and fluid language**, especially for long-range dependencies
- Combining rule-based structure (e.g., rhyme) with statistical models allows for **creative yet constrained generation**

## Future Directions

- Add a **syllable-level constraint** to control meter (e.g., iambic pentameter)
- Experiment with **Part-of-Speech (POS)-tagged** HMMs for more syntactic control
- Extend LSTM to **word-level or transformer-based generation**
