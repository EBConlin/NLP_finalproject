The model infrastructure is there, but the model itself is underperforming. Three are in the process of being implemented.
1. Adding an LSTM over the top of frozen pretrained SciBert embeddings, which has been shown to be an effective, cheap way to finetune in these cases.
2. Implementing negative sampling of the negative instances.
3. intelligently duplicating labels. Right now there is only one relation label per relation. Since "parts of same" and "contradiction" are recipricol relationships, we can add a label
to both the tokens involved instead of keeping it as one. While "supports" is not recipricol, we can cheat by adding a new recipricol relation "supported-by." Between downsampling
the negative instances by (2) and doubling the number of positive instances. It is our intention to deal with the severe class imbalance shown here.

![NLP_poster_econlin pptx](https://github.com/user-attachments/assets/99bc88f7-a14a-4511-8e5e-9c6234a59bab)
