# Towards Self-Contained Answers: Entity-Based Answer Rewriting in Conversational Search

This repository contains conversational information-seeking (CIS) data from [QReCC]([url](https://github.com/apple/ml-qrecc)), with annotated sample of 360 question-answer pairs to characterize entity saliency in CIS.
Moreover, we realease crowd workers' assessments of answer rewrite type preferences. These include both the specific type preferred and a reason for choosing the specific type in textual format.


The resources in the repository are developed for our CHIIR'24 paper: "Towards Self-Contained Answers: Entity-Based Answer Rewriting in Conversational Search", by Ivan Sekulić<sup>1</sup>, Krisztian Balog<sup>2</sup>, and Fabio Crestani<sup>1</sup>.

<sup>1</sup> Università della Svizzera italiana, Lugano, Switzerland

<sup>2</sup> University of Stavanger, Stavanger, Norway

## Entity salience annotations

[entity_salience.csv](data/entity_salience.csv) contains question-answer pairs from QReCC data, with entities extracted from the given answers. 
The entities are associated with their salience scores, which are the average of three annotations done by crowd workers.

Each row in the .csv contains:

* QID - concatenation of Conversation_no and Turn_no, indicating question ID in QReCC dataset;
* Question - question text;
* Answer - text of the answer to the question;
* Entity - entity extracted from the answer;
* Salience (float) - salience score of the entity, i.e., how essential is the entity for comprehending the answer to the question. Salience score is a real number between 0 and 2.


## Rewrite type preference

[preference_type_choice_and_reason.csv](data/preference_type_choice_and_reason.csv) contains crowd workers' annotations for the answer rewrite type preference.

Columns descriptions:

* QID - question ID in QReCC dataset;
* Question - question text;
* Input.answer_{1, 2, 3} - answer rewrites offered as multiple choice inqury to the crowd worker. It always contains (shuffled) _original_ answer, answer with inline entity explanations from _Wikibase_, and answer with clarifying _prompt_.
* Input.top_N - how many (N) most salient entities are provided explanations for or offered to clarify in the prompt;
* Preference - rewrite type preference of the worker (one of _original_, _wikibase_, or _prompt_);
* Answer.reason - textual description of the reason why the worker chose the rewrite type.


If you find the resource useful, please cite as:
```
@inproceedings{Sekulic:2024:CHIIR,
    author = {Sekuli\'c, Ivan and Balog, Krisztian and Crestani, Fabio},
    title = {Towards Self-Contained Answers: Entity-Based Answer Rewriting in Conversational Search},
    year = {2024},
    booktitle = {Proceedings of the 2024 Conference on Conference Human Information Interaction and Retrieval},
    pages = {tbd},
    series = {CHIIR '24}
}
```


