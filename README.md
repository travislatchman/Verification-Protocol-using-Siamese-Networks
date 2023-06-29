# Verification-Protocol-using-Siamese-Networks

**Brief Description:** This project involved constructing Siamese Networks that used pre-trained AlexNet and VGG16 models for feature extraction and classification. It used the Labeled Faces in the Wild (LFW) dataset, which is a verification protocol.

## Implementation:
* Constructed Siamese Networks using pre-trained AlexNet and VGG16 models.
* Performed feature extraction and classification using these models.
* Used matching algorithms (i.e. Euclidean distance, cosine angle, L1-norm, etc.) to produce scores.

## Results (Model Comparison and Performance)

### ROC curves of the Fine-Tuned Models:
![image](https://github.com/travislatchman/Verification-Protocol-using-Siamese-Networks/assets/32372013/4bb2f03d-2148-4fd9-a3df-1144047b2cde)  

Both models have comparable performance. The Siamese Network using AlexNet has an AUC-ROC of
0.83457, and the Siamese Network using VGG-16 has an AUC-ROC of 0.84215. This very small difference
could be attributed to the architectural differences between AlexNet and VGG-16. VGG-16 has a deeper
architecture with more convolutional layers, which might help it capture more complex features. But again,
it’s important to note that the difference in AUC-ROC values between the two models is not very large,
and both perform similarly well. Depending on the specific application and the computational resources
available, you might still choose to use the Siamese Network with AlexNet due to its lower computational
complexity and faster inference times compared to the Siamese Network with VGG-16. The area under the
ROC curve (AUC-ROC) in this case measures the ability of the model to correctly rank similarity scores
between different pairs of images. These values indicate that both models are reasonably good at ranking
the similarity scores for facial verification, with the VGG-16-based model having a slight edge over the
AlexNet-based model.

### ROC curves with no fine-tuning
![image](https://github.com/travislatchman/Verification-Protocol-using-Siamese-Networks/assets/32372013/41f876c6-6149-4d40-8b66-ffceb76cefc0)  

Without fine-tuning on the LFW dataset, the Siamese Network using AlexNet has an AUC-ROC of
0.77961, and the Siamese Network using VGG-16 has an AUC-ROC of 0.77056. These values indicate
the performance of the models when they are pretrained on another dataset (e.g., ImageNet) and directly
applied to the LFW dataset without any further fine-tuning. In the context of facial verification, the AUCROC values tell us about the ability of the models to distinguish between positive pairs (same person)
and negative pairs (different people) in the LFW dataset. The AUC-ROC values for both models without
fine-tuning are lower than those after fine-tuning, which suggests that the fine-tuning process improves the
models’ performance on the LFW dataset. It’s likely that the pretrained models have learned some general
features from the ImageNet dataset, which are useful for facial verification tasks, but they can still benefit
from further adaptation to the specific characteristics of the LFW dataset. Comparing the two models
without fine-tuning, the AlexNet-based Siamese Network performs slightly better than the VGG-16-based
Siamese Network with an AUC-ROC of 0.77961 vs. 0.77056. This difference indicates that the AlexNet
model might be more suitable for facial verification tasks out-of-the-box. However, it’s important to note
that the performance difference is relatively small, and after fine-tuning (the difference between the two
AUCs with no fine-tuning is even smaller than the difference with fine-tuning). Both perform similarly.
