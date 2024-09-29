# Machine Mindset: An MBTI Exploration of Large Language Models

by Jiaxi Cui, Liuzhenghao Lv, Jing Wen, Rongsheng Wang, Jing Tang, YongHong Tian, Li Yuan

https://arxiv.org/pdf/2312.12999.pdf

## Abstract
**Approach for Integrating Myers-Briggs Type Indicator (MBTI) Personality Traits into LLMs**:
- Two-phase fine-tuning and **Direct Preference Optimization (DPO)** to embed MBTI traits in large language models (LLMs)
- Ensures models internalize these traits, offering a stable and consistent personality profile

**Demonstration of Effectiveness**:
- Shows alignment between model performance and their respective MBTI traits across various domains

**Contributions**:
- Development of **personality datasets** and a new training methodology for personality integration in LLMs
- Enhances the potential for personalized AI applications
- Open-sourced the model and part of the data at <https://github.com/PKU-YuanGroup/Machine-Mindset>

## 1 Introduction

**Introduction:**
- Attention on large language models (LLMs) and their applications, especially domain-specific ones
- Shift from generic to domain-specific LLMs like ChatLaw, BloombergGPT
- Research focus on long-form text handling and personalized models
- Customization of models based on Myers-Briggs Type Indicator (MBTI) as a research direction
- Lack of corresponding datasets for this research, leading to simplistic approaches with limited effectiveness

**Methodology:**
- Introducing "Machine Mindset" concept
- Injecting specific MBTI personality types using two-phase fine-tuning and Direct Preference Optimization (DPO)
- Personalized models internalize personality traits, avoiding disarray issues
- Capabilities vary depending on the specific MBTI personality type

**Contributions:**
1. Proposed method for constructing personality datasets and building behavior/self-awareness datasets
2. Training method including two-stage supervised fine-tuning and DPO to inject a specific personality into the model
3. Capable of learning behavioral patterns and acquiring self-awareness corresponding to that personality
4. Extensive testing across various domains, showing performance alignment with personality traits
5. Consistent training data and processes, reducing reliance on specific LLMs for integration.

## 2 Related Work

**Related Work**
- Previous studies have tested personalities of large language models using prompting techniques [4;3]
- Methods rely on standard personality testing methods adapted for language models
- Stability and clarity of derived personality traits remain contested

**Myers-Briggs Type Indicator (MBTI)**
- Developed by Katharine Cook Briggs and Isabel Myers [1]
- Classifies individuals into 16 specific personality types based on four dichotomous dimensions:
  - **Energy**: Extraversion (E) vs Introversion (I)
  - **Information**: Sensing (S) vs Intuition (N)
  - **Decision**: Thinking (T) vs Feeling (F)
  - **Execution**: Judging (J) vs Perceiving (P)
- Provides insights into how individuals perceive and interact with the world, make decisions, process information
- Personality types are unique combinations of these dimensions

**Previous Research on General LLMs**
- Examined diversity of personality types exhibited by different models [5]
- Study had language models complete MBTI assessment questions to assess and compare personalities
- Initial step towards understanding how architecture and training data influence personality traits within the context of MBTI.

## 3 Method

**Behavior Datasets**
- Purpose: Train LLMs to respond consistently with specific personality traits
- Customized Alpaca dataset for modifications
- Engaged ChatGPT in classification task to determine MBTI dimension
- Generated responses reflecting two attitudes within identified dimension
- Resulted in diverse datasets for supervised fine-tuning
- Composition ratios: "Energy" minimal, "Information" predominant
- Called **behavior datasets** due to their purpose of enabling LLMs to generate language responses corresponding to different personalities

**Self-awareness Datasets**
- Bridge the gap between behavior and self-awareness datasets
- Comprised of Q&As elucidating 16 personality types of MBTI
- Majority questions are direct or indirect inquiries about personalities
- Answers involve descriptions of one's own personalities
- Generated by ChatGPT guided by certain prompts

**Fine-tuning LLMs towards a certain personality**
- Imparted different personalities through supervised fine-tuning
- Two-stage process using behavior and self-awareness datasets, respectively
- Used four datasets corresponding to "I," "N," "F," and "P" from behavior datasets for first stage of fine-tuning
- Retrieved extra dataset aimed at enhancing self-awareness as an INFP individual for second stage of fine-tuning
- Employed Low Rank Adaptation (LoRA) for efficiency and modularity in supervised fine-tuning

**Direct Preference Optimization (DPO)**
- Alternative to Reinforcement Learning from Human Feedback (RLHF) in LLM alignment
- Enables LLM to distinguish a preferred response from a given pair
- Process involves obtaining datasets of two attitudes within one dimension, such as "F" and "T" in the "Decision" dimension
- Conduct DPO, allowing LLM to prefer "F" responses over "T" responses

**Evaluation Method**
- Evaluated trained LLMs using existing MBTI questionnaire with slight modifications for clarity and comprehensibility
- Objective: Demonstrate that model exhibits desired personality traits
- Results should not be considered definitive due to limitations of multiple-choice format questionnaire
- Conducted supplementary tests to investigate how various personality traits impact the performance of LLMs.

## 4 Experiments and Results

**Experiments and Results**

**Training Process**:
- Combination of Supervised Fine-Tuning (SFT) and Direct Preference Optimization (DPO) used to infuse personality traits into large language models (LLMs)
- SFT refines language generation capabilities, while DPO reinforces specific personality traits for deeper integration
- LLMs trained on 16 MBTI personality types in English and Chinese

**Evaluation Results**:
- Criteria: MBTI questionnaire testing, performance metrics, user feedback assessment
- **MBTI Questionnaire Testing**: Assesses if LLMs exhibit consistent personalities with their assigned MBTI types using modified questionnaires
- **Performance Metrics**: Measures language generation quality, coherence, relevance of responses across tasks and domains
- **User Feedback Assessment**: Collects user perception and satisfaction when interacting with different personality-tuned LLMs

**Ablation Experiments**:
- Explores how the balance or imbalance in training data for MBTI personality dimensions impacts resulting models
- Varies dataset compositions to uncover correlations between data distribution and model's personality traits and performance

**Effects on Abilities**:
- Investigates whether imbued personality traits influence LLMs' reasoning, understanding, and cognitive capabilities
- Subjects models to various tasks and tests to elucidate interplay between personality and cognitive functions in LLMs.

### 5 Conclusion

**Conclusion**
* Explored intersection of LLMs and Myers-Briggs Type Indicator (MBTI)
* Aimed to imbue models with distinct personalities based on MBTI types
* Used Supervised Fine-Tuning (SFT) and Direct Preference Optimization (DPO) for training
* Successfully cultivated diverse range of LLMs, each representing an MBTI type in English and Chinese
* Experiments showed alignment between personality-tuned models' traits and designated MBTI types
* Contributes to advancing AI personalization field
* New applications: natural language understanding, dialogue generation, human-computer interaction
* Ablation experiments revealed significance of dataset composition on shaping personality-tuned models
* Insights into training dynamics and adaptability of LLMs to diverse personalities
* Limitations: use of MBTI questionnaire, focus on text-based tasks
* Promising step towards enhancing personalization and adaptability of LLMs.
