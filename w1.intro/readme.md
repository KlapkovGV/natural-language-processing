# Introduction to Natural Language Processing

Natural Language Processing is referred to as NLP in English literature. It is a subcategory of Artificial Intelligence.

In the world of computing, there are two distinct types of languages:
1. Machine Learning
2. Natural Languages

Programming languages are Context-Free (they have strict rules and no ambiguity), whereas Natural Languages are Context-Dependent and highly ambiguous (slang, sarcasm, metaphors), which is why NLP is so difficult for computers.

NLP is defined as the process by which machines take and process the language spoken by humans. In technical terms, NLP is usually divided into two main components:
1. Natural Language Understanding: how machines understand what we say;
2. Natural Language Generation: how machines produce human-like text.

## Purpose of NLP

The aim of NLP is to create systems capable of deriving meaning from text and performing tasks such as translation, grammar checking, topic classification.

## The NLP Pipeline

NLP processing is not a sigle step; it is a hierarchical sequence of analyses that allow a machine to understand human language. Because languages vary significantly, the system follows these levels:
1. Morphological and Lexical Analysis

The system identifies individual words and analyzes their internal structure. It breaks down words into **roots and affixes**.
* This is especially vital for agglutinative languages where a single word can convey complex meanings through multiple suffixes.

2. Syntactic Analysis (Parsing)

This stage focuses on the arrangement of words in a sentence. The goal is to understand the grammatical relationship between words and ensure the sentence follows the rules of the language's syntax.

3. Semantic Analysis

This level deals with the literal meaning of the text. It maps syntactic structures to their real-world meanings, attempting to resolve ambiguity in what the words actually represent.

4. Pragmatic and Discourse Analysis

Discourse analysis examines how the meaning of a sentence depends on the sentences that came before it. Pragmatics focuses on the context and intent. It helps the machine understand hidden meanings, such as sarcasm or metaphors, and the overall purpose of the conversation.

## Text Normalization

In the preprocessing stage of any NLP pipeline, the primary goal is to reduce the vocabulary size and group together different forms of the same word. This process is known as **Text Normalization**. Without this step, a computer would treat "walk", "walking", and "walked" as three entirely different concepts, thich is inefficient for analysis.

1. The Heuristic Approach: Stemming

Stemming is the process of reducing a word to its "stem" by crudely chopping off its suffixes. It is a heuristic method, meaning it follows a set of hard-coded rules (like if the word ends in -ing, remove it) rather than understanding the language's grammar.

A stem is the part of the word that remains after the chopping process. It is important to note that a stem does not always have to be a valid, meaningful word.

Because stemming is an aggressive process, it can lead to over-stemming. For example, in Turkish, words like yer (place), yemek (to eat), and yeter (enough) might all be reduced to the same stem: "-ye". The machine now treats three unrelated concepts as the same, leading to a loss of semantic context.

2. The Linguistic Approach: Lemmatization

Lemmatization is a more sophisticated and precise method of finding the base form of a word. Unlike stemming, it performs a full morphological analysis and usually checks a dictionary (lexicon) to ensure the result is accurate.

The Lemma is the result of this process (the canonical or dictionary form of the word).

Lemmatization understands the relationship between words. In English, Lemmatization is crucial because many words change their form entirely based on tense or quantity.

| Input Word | Stemming (Heuristic) | Lemmatization (Morphological) | Why the difference? |
| :--- | :--- | :--- | :--- |
| **Studies** | `studi` | **study** | Stemming just chops the "es". Lemma finds the dictionary form. |
| **Caring** | `car` | **care** | Stemming incorrectly reduces "caring" to "car". Lemma understands the verb "care". |
| **Went** | `went` | **go** | Stemming can't handle irregular verbs. Lemma recognizes "went" as a past tense of "go". |
| **Better** | `better` | **good** | Lemma connects the comparative adjective to its base form. |
| **Feet** | `feet` | **foot** | Lemma understands irregular plurals. |

Part-of-speach awareness:
- the word: Saw;
- stemming: returns saw;
- lemmatization:
  - if used as: He saw a bied, the lemma is see;
  - if used as: He used a saw, the lemma is saw.

3. Roots vs. Stems

While people often use these terms interchangeably, they are technically different. **Root** is the primary lexical unit that carries the core meaning and cannot be broken down further. **Stem** is the base form specifically used for attaching grammatical inflections. 

