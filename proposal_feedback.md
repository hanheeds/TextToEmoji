Score: 3/8

You’re on the right track, but there are some specifics missing that you should try to incorporate into your revised proposal. In particular, you should make it clear how you want to train your models and what kinds of hyperparameters you might want to adjust. You should also try your best to avoid just manually curating a list of emojis that correspond to certain emotions. If you want to train a model to use emojis, you should find a dataset that incorporates emojis. You have a week to submit a revised proposal and earn additional points, but feel free to reach out before then if you have specific questions about this feedback.

We discussed this briefly, but because you have multilabel classification (a given example can have multiple labels), your loss function needs to be a bit more complicated than what we’ve covered in class. The easiest is probably just to enumerate all 27 emotions and treat your loss as a combination of 27 different Binary Cross Entropy losses that you just take a (possibly weighted) average over. Otherwise you could look more into multilabel losses.

How will you do train/test splits? Can you clarify whether your data has predetermined splits?

Logistic regression would be worthwhile just try as a baseline, since it’s extremely easy to train and your neural model should be able to do much better.

Essential goals:
-	Formatting issue; move your first essential goal below the parenthetical.
-	What do you mean by “the right parameters?” How does this differ desired goal #1? Please clarify this and try to provide specifics.

Desired goals:
-	What do you mean here as the difference between training and fine-tuning; what’s the difference between those in this setting?
-	Try to avoid framing this in terms of accuracy; what will you do to try to improve your accuracy? What will you do to avoid overfitting?
-	Come up with a more specific plan for how you will map from emotion labels to emojis. You should avoid just manually creating a dictionary that does that mapping. I don’t have a specific dataset in mind for you to use to train a model that might be able to do so, but I bet you can find one. A starting point to look at would be [this paper](https://paperswithcode.com/paper/emoji2vec-learning-emoji-representations-from) that trained word embeddings on many emojis and looked at how they correlated with coarse sentiment classification. It’s been cited many times, and some of those have probably applied these embeddings to analyses of text that contains emojis.

Stretch goals:
-	How will you train this multiple emotion model? Again, this shouldn’t be done by hand as part of this class; you should try to focus on something compatible with deep learning.
-	User interface sounds cool, but that might be slightly out of scope for this class. Can you propose a different stretch goal? You might consider something like model distillation or explainability to speed up or interpret your model.
