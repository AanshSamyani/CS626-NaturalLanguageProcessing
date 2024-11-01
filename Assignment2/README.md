## Assignment 2 - Conditional Random Fields (CRF) based Part of Speech Tagging (POS - Tagging)
This is my implementation for POST Tagging on Brown's Dataset using CRFs. The above implementation makes  use of the **'universal_tagset'** for POS tagging. 
POS Tagging is a basic Sequence to Sequence Mapping NLP Technique. A couple of examples of POS Tagging are:
1) Input --> "Reading is an essential skill."
   Output --> "Reading" - "NN" (Noun)
              "is" - "BEZ" (Auxilary Verb)
              "an" - "AT" (Article)
              "essential" - "JJ" (Adjective)
              "skill" - "NN" (Noun)

2) Input --> "The grand jury said."
   Output --> "The" - "AT" (Article)
              "grand" - "JJ" (Adjective)
              "jury" - "NN" (Noun)
              "said" - "VBD" (Verb - Past Tense)   

Conditional Random Fields (CRFs) are a type of probabilistic graphical model (discriminative in nature) used for structured prediction, commonly applied in tasks like Part-of-Speech (POS) tagging in Natural Language Processing (NLP). CRFs model the conditional probability of a sequence of labels given a sequence of observed inputs, allowing them to account for contextual dependencies between neighboring labels. This makes CRFs particularly effective for sequence-based tasks where the label of each item in a sequence depends on others.

In POS tagging, CRFs are used to predict the correct part of speech for each word in a sentence by leveraging the context provided by surrounding words. For instance, the tag for "bank" can vary depending on nearby words ("river bank" vs. "bank account"). CRFs define a global conditional probability over the entire sequence, making them less prone to errors that might arise from independently tagging each word. By incorporating feature functions based on words and their contexts, CRFs can effectively capture and represent dependencies, enabling more accurate tagging compared to simpler models. This structured approach is why CRFs are widely used for POS tagging in NLP, particularly when label dependencies play a crucial role.

**Visualization of Conditional Random Fields:**
<div align="center">
   <img src = "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRqeEPfew1wRtYRd9TrG0YmwDnQaEcvR5CwqA&s">
</div>

**Training and Evaluation:** The CRF was trained on the Brown dataset corpus, the evaluation involved a 5-fold cross validation. The training resulted in an average accuracy of **0.974** per fold. The confusion matrix after 5 folds of validation looks like this:

<div align="center">
   <img width="800" alt="Screenshot 2024-11-01 235713" src="https://github.com/user-attachments/assets/ac468161-6d20-4b96-aa0e-bcc845486c4f">
</div>

**Problems faced in CRF based POS Tagging:**
1) **Feature Engineering:** CRFs depend heavily on hand-engineered features. Selecting informative features can be labor-intensive, requiring domain expertise and understanding of linguistic nuances, which may not always be feasible for large or diverse datasets.
2) **Limited Long-Range Dependencies:** While CRFs capture local dependencies well, they struggle with long-range dependencies within a sentence. In POS tagging, certain tags can depend on words further away in the sequence, which CRFs cannot model as effectively without extensive, custom feature design.
3) **Scalability for Large Datasets:** In practice, applying CRFs to very large datasets or corpora may be challenging, as the model doesn’t inherently scale well. As a result, for large-scale tagging applications, faster, more scalable alternatives like neural sequence models are sometimes preferred.
