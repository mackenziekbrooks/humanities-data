In this section, we'll learn about ways of using the computer to read and texts. 

Much of the material in this section was adapted (with permission and blessing) from the [Text Analysis Coursebook](http://walshbr.com/textanalysiscoursebook/) written by Sarah Horowitz and Brandon Walsh. 

[TOC]

## Close Reading

Text analysis is something that we all engage in, whether we realize it or not. The term is broad and capacious and encapsulates a variety of different activities. Even something as simple as slowing down when you see a stop sign is a kind of text analysis: doing so means you have parsed the meaning of the words on the sign and reacted accordingly.

Indeed any of the following, related activities are forms of text analysis:

* Paraphrasing a text
* Searching for hidden meanings in a text
* Adapting a text and reflecting on it
* Examining the details in a text

This last point is worth pausing over: close reading, in particular, is often proclaimed as one of the primary analytical tool of scholars and students in the humanities. To read closely means to give careful attention to the various components that make up a text, ones which cause us to think or feel a certain way about it. Close reading relies on a core principle about the text under study:

> Everything about the text matters, whether the author intended for it to matter or not.

Consider the following thought experiment. One day you come home to find the following note from your roommate on the counter:

``` took care of these dishes? Thanks.```

Next to the note: dirty dishes. Was your roommate in a hurry and actually asking you to wash dishes? Or were they sarcastically trying to give you grief for not having done your part? Lots of questions. To imagine responses to them you might employ a range of assumptions and interpretations depending on the scenario:

* Context: you have been growing more and more irritated with your roommate for some time now. Their actions just really get under your skin: dirty dishes, laundry everywhere, the works. They clearly meant the note as an insult.

* Author: your roommate is actually a great person and would never leave a passive aggressive note. In fact, they probably meant it as a joke.

* Text: Take a look at that question mark. And then the curt second sentence. Your roommate put those things there on purpose to be rude.

The list could go on and on. We employ a similar range of skills when we read anything, be it fiction, poetry, or historical documents. Close reading might be best described as an activity in which a reader simply lets no detail of the text go unquestioned. The best way at approaching a good close reading is by asking (and attempting to answer) questions about every piece of a text.


## How Computers Read 

We've talked about how computers and humans have their respective skills. With respect to text analysis, we can say that computers and humans have complementary skills. Computers are good at doing things that would take us a long time to do or that would be incredibly tedious. Computers can easily count and compare and will do so for pretty much as long as you tell them to do so. In contrast, humans are very good at understanding nuance and context. Thus, you wouldn’t want a computer to do any close reading, or unpack the claims of a primary or secondary text; this is something you are far better at. By the same token, it’s probably easier to have a computer list all the numbers between one and 45678987 than to do it yourself.

Before we start analyzing texts, we need to know how computers understand text. Consider the following sentence:

“We saw 8 1/2.”

Taken alone, the sentence doesn’t tell us much. Its meaning depends a lot on the question to which we might be responding, and we can think of two possible questions with very different contexts:

* “How many movies did you see?

* “What movie did you see?”

In the first case, we might be responding with the number of movies that we had seen. It was a slow weekend, and we spent it at the local movie theater hopping from film to film. It was a great time! In the second situation, we might be responding with the title of a specific film, 8 1/2 by Italian director Frederico Fellini. So one answer is a number, and one answer is a name. Since humans are good at grasping context, we would easily be able to distinguish between the two. In most situations, we would just adjust our understanding internally before moving on with the conversation.

Computers cannot make inferences like these, and this fact has serious implications: numbers and words have significantly different uses. Here are two further extensions of the conversation:

* If you add four to how many movies you saw, what is the result?

If we were talking about a number of movies, my response would clearly be, “Oh that’s 12.5. Why are you giving me a math quiz?” If we were talking about the Fellini film, we might respond, “What? Oh, we were talking about a title, not a number. We can’t add things to a title.” Again, humans have the ability to respond to context, infer, and adapt. Computers aren’t nearly as flexible: they need to know ahead of time, in most cases, what kind of information they are dealing with. That way they can act as you anticipated.

We learned earlier about the concept of "data types." Well now they matter! In the above example, we encountered: 

* Strings: characters, the stuff of words
* Integers: a whole numbers

The distinction between strings and integers is important for text analysis. You can perform arithmetic operations on integers while strings respond less well to such things. You can capitalize words, but not numbers. And computers generally want you to deal with similar objects: you can combine strings (words can become sentences) or add numbers, but trying to combine a string and an integer will break things. To be clear to the computer which data type we mean, we use can indicate strings with "quote" marks and integers without. `8` vs. `"8"`. In response, the computer wants us to to know that it doesn't know that `"8"` is related to `"Eight"` or `"Eighth"` or even `"eight"`.

It might seem surprising that computers aren't smarter than that, but it brings us to one of the first steps in text analysis: tokenization, or the process by which we break apart all of the words and punctuation in a text into separate tokens. "I love you" becomes "I", "love", "you", ".".

We can break things down even further once we’ve divided a text into individual words. While we often care about how many times each particular token or word occurs, we might also care about the different kinds of words. We might want to keep track, on the one hand, of all the different words in a text regardless of how often they occur. But we might also want a different kind of vocabulary list. Rather than counting all the words, we might just want to grab a single example of each token type. If we have the following document:`Test test test sentence sentence`

We have five tokens and two types (‘test’ and ‘sentence’). A list of types might be good for getting a sense of the kinds of language used in a text, while a raw list of tokens could be useful for figuring out what kinds of words occur in which proportions. Depending on our research questions and interests, statistics like these can help us figure out what the document discusses as well as how it is being discussed.

If sentences are broken up into words, we might care also about breaking documents into sentences first. We have a name for that too: segmentation.

    “But wait,” you say, “computers care about capitalization. So if we tokenize a text and try to compare ‘word’ and ‘Word’ they will think they are entirely different things!”

Good catch! You’re right, those differences in capitalization often aren’t meaningful. It is a fairly common practice to lowercase all the words after you tokenize them. This process is often called normalizing the data, since we are smoothing out inconsistencies that might get in the way of our research questions. This whole collection of processes of segmentation, tokenization, and normalization has a name of its own as well: preprocessing, all those things you do to data before you work with it. Depending on your interests, you might include other steps, such as tagging tokens for parts of speech or filtering out particular types of words. Note that preprocessing can change your list of types. A computer would not recognize “Said” and “said” as being of the same type, but, if you normalize capitalization so that every token is lowercased, a computer would see them as the same word. So you often need to decide what pieces you care about at the beginning of the process.


## Bag of words
When we read, our eyes move in sequence across the page and take in phrase after phrase in the order in which they were intended. This sense of chronology is integral to how we, as human readers, understand texts. But it is possible to imagine other ways of reading. Have you ever skimmed over a page backwards looking at every other word? You probably still got the gist of the text even though you didn’t read it in order and even though you missed many of the words.

If we take the words in a text as being indicative of its underlying topics, we actually don’t need to worry about word order so much. The sequence of words, sometimes called the *syntagmatic axis*, only matters for certain kinds of reading. But we can find out interesting things about texts if we are a little more flexible and think about them not as things that unfold over time but rather as pure token counts, as bags of words. In a *bag of words* model, word order becomes irrelevant. All we care about is what words occur in a text and how often they do so. 

You can use a bag of words approach to determine how different or similar whole books or authors are from each other. If we have lists of words for each text as well as for the corpus (or set of documents) as a whole, we can actually work backwards to get a sense of the underlying topics that we were talking about a moment ago. Instead of skimming a paragraph to determine its basic topic, we could scan full texts – and scan lots of them. And rather than trying to get a sense of 1-3 topics, we could break our text apart into 15-20 different topics. Now we are cooking with gas, and we’re talking about topic modeling.

## Topic Modeling

Given enough time and energy, we can imagine a tool that would infer topics for us without us having to read all of our documents first. The approach that we will take is a technique called **topic modeling**, a computational method that allows you to discover the topics that construct a text. Topic modeling does so by exercising a variety of statistical protocols over and over again on a text. 

Topic modeling involves some complex statistics, so the following description might seem a bit hand-wavey.  Topic modeling software looks for words that tend to occur next to each in statistically significant ways. The sum total of these words that occur next to each other becomes legible to a reader as a topic. Unlike the human brain, topic modeling software can process hundreds of thousands of texts, over and over again, refining its sense of how all the pieces fit together. It can give us a sense of the themes and discourses that run beneath an entire corpus.

So when you run topic modeling software, it looks for words that occur near each other in texts in meaningful ways over the course of the corpus. In most cases, it looks for words that occur in documents together. Remember, these words are not dependent on their location within the document. Topic modeling works on a bag of words model that only cares about whether or not the words occur within the text, not their position within it. But you might occasionally chunk larger documents into a series of paragraphs so that the software thinks about them each as separate documents for finer granularity. There are a number of similar tricks for refining your processes.

Until now, we have stressed approaching text analysis with a clear sense of your interests and the research questions that drive them. Topic modeling works a little differently: it is more useful for exploratory work. We call topic modeling unsupervised classification because we are asking the computer to analyze and mark a text without giving it any clear directions. We just say, “here is some text. Do your thing and tell me what you find.” A supervised classifier would take information from us to help it make decisions. We might say, “read this text. If it has more than fifty uses of the word ‘crime’ mark it as ‘detective fiction.’ If it has fifty uses of the word ‘love,’ mark it as ‘romance’” (more on supervised classifieres in the next chapter). Unsupervised classifiers like topic modeling instead know very little about the underlying texts that they are examining. Instead, they process them based on an underlying model.

In the last lesson we called the bag of words model an epistemology of texts, a way of understanding documents that might be different from what you were familiar with. In the case of the kind of topic modeling we have been discussing, that model could further be called Latent Dirichlet Allocation (LDA). We won’t go into any detail about the specifics of LDA, but it is important to know that this is the model you are working with and that LDA assumes that a text is constructed from a small number of topics.

Don’t be alarmed if topic modeling seems much more abstract than the material we have covered until now. To really understand how topic modeling works under the hood, you will need to have a grasp of a variety of different topics in machine learning and statistics. We are not so concerned that you understand these specifics. We care, instead, that you understand the idea behind it, have some sense of how to read make sense of other topic modeling projects, and be able to explain them to others in general terms.


## Sentiment Analysis 