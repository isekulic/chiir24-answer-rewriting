## Entity salience annotations

[entity_salience.csv](entity_salience.csv) contains question-answer pairs from QReCC data, with entities extracted from the given answers. 
The entities are associated with their salience scores, which are the average of three annotations done by crowd workers.

Each row in the .csv contains:

* QID - concatenation of Conversation_no and Turn_no, indicating question ID in QReCC dataset;
* Question - question text;
* Answer - text of the answer to the question;
* Entity - entity extracted from the answer;
* Salience (float) - salience score of the entity, i.e., how essential is the entity for comprehending the answer to the question. Salience score is a real number between 0 and 2.


## Rewrite type preference

[preference_type_choice_and_reason.csv](preference_type_choice_and_reason.csv) contains crowd workers' annotations for the answer rewrite type preference.

Columns descriptions:

* QID - question ID in QReCC dataset;
* Question - question text;
* Input.answer_{1, 2, 3} - answer rewrites offered as multiple choice inqury to the crowd worker. It always contains (shuffled) _original_ answer, answer with inline entity explanations from _Wikibase_, and answer with clarifying _prompt_.
* Input.top_N - how many (N) most salient entities are provided explanations for or offered to clarify in the prompt;
* Preference - rewrite type preference of the worker (one of _original_, _wikibase_, or _prompt_);
* Answer.reason - textual description of the reason why the worker chose the rewrite type.
