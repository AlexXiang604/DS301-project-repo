# Deepfake Facial Imagery Detection

## Overview
This project aims to develop a sophisticated classifier capable of discerning genuine images from those fabricated by AI technologies, with a focus on efficiency for deployment on mobile devices. Utilizing MobileNet V1, our classifier achieves high accuracy in detecting AI-generated images and provides valuable insights into the decision-making process via Grad-CAM.

## Team Members
- Alex Zhang
- Apple Jin
- Alex Xiang

## Motivation
AI-generated and modified imagery technology has found extensive applications across various domains, from generating captivating fake photos for social media engagement to deploying forged imagery to discredit opponents during elections, fabricating academic papers, and even executing extortion schemas1 2. Despite its vast potential, this technology harbors significant adverse consequences. Studies have shown that most Internet users place undue trust in online images and seldom question their authenticity3. Additionally, in academic publishing, fake scientific images frequently evade detection4. These scenarios underscore the urgent need to develop proficient fake image detection methodologies to match the rapid advancements in AI-driven image generation and modification, enabling timely identification and mitigation of challenges posed.
Given the significant role of applications of AI-generated facial images in a spectrum of applications, from crafting memes for daily amusement to spoofing facial recognition systems and facilitating fraudulent activities, this project specifically focuses on face-centric images. Our objective is to provide an effective method to detect AI-generated fake face images to meet the evolving challenges of digital authenticity.

## Related Work
- **CNN Detection of GAN-Generated Face Images based on Cross-Band Co-occurrences Analysis**
- **Uniqueness:** Robustness to Post-processing: Demonstrates strong robustness against various
post-processing modifications such as JPEG compression, blurring, and resizing, maintaining high detection accuracy.
- **Limitation:** Dependence on Specific Data: The model's performance can decrease significantly under mismatched conditions that weren't covered during training, particularly evident in scenarios with different JPEG compression levels.
- **An Improvised CNN Model For Fake Image Detection**
- **Uniqueness:** Performance Comparison: Proved the superior performance of DenseNet, ResNet50 and MobileNet on the task of recognizing true and false pictures, which inspires our choice of model.
- **Limitation:** Dependence on Specific Data: The test results are derived from an unopened-source dataset produced by human experts, and performance on ai generated datasets is not validated.

## Methodology
- **Model Initialization**: MobileNet V1 initialized with ImageNet-pretrained weights.
- **Training**: Models were trained with variations in hyperparameters and datasets. The baseline model used GAN-generated images, expanded later to include images from Stable Diffusion (version 1.5, 2.1, XL1.0).
- **Preprocessing**: Implementation of Error Level Analysis (ELA) to detect manipulated regions.
- **Model Configurations**: Tested various configurations, including dropout rates and unfreezing different layers for fine-tuning.

## Results
The models were evaluated based on their ability to detect AI-generated images from different sources:
- **Baseline Model**: High accuracy on GAN-generated images but poor on others.
- **Enhanced Models**: Models trained on a combination of GAN and Stable Diffusion images showed improved accuracy across various datasets.

## Analysis
Our results suggest that using a diverse dataset significantly enhances the model's ability to generalize across different types of synthetic imagery. ELA as a preprocessing tool did not significantly improve performance, whereas dataset diversification did.

## Conclusions
The project demonstrated the capability of MobileNet in deepfake detection, emphasizing the importance of diverse training datasets. Future work will focus on expanding the dataset to include more varieties of AI-generated images and refining classification thresholds.

## Future Work
- **Data Expansion**: Include images from newer AI technologies like MidJourney and DALL-E.
- **Refinement**: Adjust classification thresholds to optimize performance in specific user settings.
- **Utilization of Grad-CAM**: Besides enhancing model transparency and interoperability, the Grad-CAM insights can also be leveraged for targeted classifiers.
