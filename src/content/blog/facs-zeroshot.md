---
title: "FACS and Zero-Shot Learning"
description: "Having kept Ekman et al.'s Facial Action Coding System in tight rotation during my diss research, an idea sprung to mind..."
pubDate: 2026-08-05
tags: ["Tech", "Discussion", "Deep Learning", "FER", "FACS"]
---

My endeavours with researching and training transformer models with the goal of classifying particular facial expressions left me with lots of interesting results, ideas for improvements, and questions for what can be pushed forward with this field of study in AI.

The "what-ifs" began to cascade as I sat in at a Computer Vision lecture earlier this year at the University of Exeter, about zero-shot learning. Zero-shot learning is a method that allows artificial intelligence models to classify previously unseen types. It achieves this by pre-training the model on broad patterns surrounding the topic, and utilising text descriptions or other mediums as auxiliary information for which the model can infer new classes. For instance, if our auxiliary data has information such as "a horse-like animal with stripes" and the model's pre-training includes horses, without explicit training on zebras, the model can classify the previously unseen zebra class.

My thoughts immediately went to my dissertation on Facial Expression Recognition. A key impetus behind this field of study in conjunction with computer vision is Ekman et al.'s <a href="https://www.paulekman.com/facial-action-coding-system/" target="_blank" rel="noopener noreferrer" class="text-blue-600">Facial Action Coding System (FACS)</a>, which introduced numbered "Action Units" to identify unique visual changes triggered by muscle movement in the face. For example, AU 1 represents the Inner Brow Raiser, which could indicate sadness or surprise.

My question I raised to my lecturer was about FER; up until this point, my understand of detecting and classifying expressions had been that a cascade classifier combs the image to find the face, and said face as a whole is processed to achieve a classification. What I wanted to know was, can cascade classifiers identify specific regions or muscle twitches on the face (instead of the face as a whole), to instead assess the presence and positioning of different action units? If computer vision models could instead analyse the presence of AUs, utilise text-based descriptors of each AU as auxiliary data and have introduce a classification mechanism in such a way that for instance:

"AU 4 (Brow Lowerer)" + "AU 6 (Cheek Raiser)" both present, therefore "Expression: Angry"

FER would no longer be bound to the labeled classes in a dataset, but to the 7,000-10,000 different combinations of muscle movements FACS can facilitate with its 46 different AUs!! It would be absolutely groundbreaking; the datasets I experimented with was limited to 7 classes (expressions) and had heavy class imbalance. Should zero-shot learning be applied to FER as I theorise it, computer vision models can facilitate a vast variety of facial expressions, and their comprehension of emotions can be developed further.

Zhao et al. have experimented with the concept in 2024 <a href="https://arxiv.org/abs/2405.19100" target="_blank" rel="noopener noreferrer" class="text-blue-600">here!</a>
They proposed Exp-CLIP, which transfers task knowledge (auxiliary data) from LLMs and incorporates their projection head to map the vision-language space to the space that captures representations of facial actions. Subsequent zero-shot predictions are accomplished via their proposal of aligning the visual representations with task-specific semantinc meanings derived from the LLM. This gained superior results to standard CLIP models (multimodal AI models that connect visual learning to text via NLP), showing me this concept has been played around with previously for FER! It would exciting to research this application of ZSL towards FER further, maybe push the envelope further by myself???

This has been an interesting sub-division of the research into FER, and one that I'd like to experiment with in the future: if my hypothesis is correct, it would allow for the classification of countless facial expressions beyond the defined labels, massively expanding the potential for which FER applications can run with. But hey, just an idea for now!
