# Predict-Closed-Question-StackOverFlow
Millions of programmers use Stack Overflow to get high quality answers to their programming questions every day.  We take quality very seriously, and have evolved an effective culture of moderation to safe-guard it.

With more than six thousand new questions asked on Stack Overflow every weekday we're looking to add more sophisticated software solutions to our moderation toolbox.

Closing Questions

Currently about 6% of all new questions end up "closed".  Questions can be closed as off topic, not constructive, not a real question, or too localized.  More in depth descriptions of each reason can be found in the Stack Overflow FAQ.  The exact duplicate close reason has been excluded from this contest, since it depends on previous questions.

Your goal is to build a classifier that predicts whether or not a question will be closed given the question as submitted, along with the reason that the question was closed.  Additional data about the user at question creation time is also available.


# Dataset Link
https://www.kaggle.com/competitions/predict-closed-questions-on-stack-overflow/data

# Dataset Description
The training data contains data through July 31st UTC, and the public leaderboard data goes from August 1 UTC to August 14 UTC.

The train.csv file contains post text and associated metadata at the time of post creation which will serve as inputs to your solution.  The state of the post as of July 31st is also included. It contains the following fields (not in this order):

- Input
- PostCreationDate
- OwnerUserId
- OwnerCreationDate
- ReputationAtPostCreation
- OwnerUndeletedAnswerCountAtPostTime
- Title
- BodyMarkdown
- Tag1
- Tag2
- Tag3
- Tag4
- Tag5
- Output
- OpenStatus
- Additional Data
- PostId
- PostClosedDate

The public leaderboard data contains all of the above fields, except for the target field OpenStatus and PostClosedDate.

The file train-sample.csv is a stratified sample of the training data: it contains every closed question and an equally-sized random sample of the open questions in the training data.

All questions will have a value in Tag1, but Tags 2 through 5 are optional.

To convert the user submitted Markdown found in BodyMarkdown to HTML if desired, our open source implementations in C# and Javascript may be useful.

Additional data can be found in "2012-07 Stack Overflow.7z", which contains an entire public data dump of Stack Overflow.  Descriptions of the values can be found in the archive itself as well as on Meta Stack Overflow.  This data will not be available as inputs, but may be useful in building your solution.  As it is rather large (6GB) you may find it easier to download as a torrent, more details can be found in this forum post.


Using 8000 smaples only from data to can fit in the memory

# Feature Engineering:
- Drop nulls
- extraxt important features as title, BodyMarkdown and OpenStatue
- Remove Puncatutiond 
- Encode Labels using LabelEncoder
- Use TfidfVectorizer to extract features from data

# Models:
  - MLP Classifier
  - ANN
  - SVM

# Models Evalution:
1. MLP Classifier
  - Accuracy = 62.6 %
2. SVM
  - Accuracy = 63.1 %
3. ANN
  - Accuracy = 58.4 %


