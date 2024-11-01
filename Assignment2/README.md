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
   <img src = "[https://www.google.com/url?sa=i&url=https%3A%2F%2Fslideplayer.com%2Fslide%2F4136134%2F&psig=AOvVaw2he1u5XK0VbzI-rel9hcWC&ust=1730571696024000&source=images&cd=vfe&opi=89978449&ved=0CBQQjRxqFwoTCND9lZfgu4kDFQAAAAAdAAAAABAE](https://slideplayer.com/slide/4136134/13/images/22/Conditional+Random+Fields.jpg)">
</div>
