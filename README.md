# SPINOS: A Dataset of Subtle Polarity and Intensity Opinion Shifts

You will need Python>=3.8 and the following package to be installed:
```
pip install pandas==1.3.4
```

You can read the data with:
```
import pandas as pd

data = pd.read_pickle('data/SPINOS_dataset.pkl')
```

The dataframe contains the following columns:

- `topic` *(str)*: The topic this statement is about.

- 'users' *(str)*: Which user has posted this particular post. *Note:* The usernames are completely anonymus and the names are in the form: 'user_0', 'user_1', etc.

- `annotation` *(str)*: Majority vote of the non-expert annotators.

- `exp_annotation` *(str)*: Annotation assigned by the expert annotators.

- `s_against` (strongly against), `against` (weakly against), `stance_not_inferrable`, `favor` (weakly in favor), `s_favor` (strongly in favor) *(int)*: Count of how many times the annotators assigned the corresponding stance.

- `is_explicit` *(str)*: The stance is explicitly stated. Values = \['No', 'Yes'\].

- `is_sarcastic` *(str)*: The stance is sarcastic. Values = \['No', 'Yes'\].

- `timestamp` *(pandas Timestamp)*: Date and time when the post was posted.

- `toplevel_id` *(str)*: ID of the top-level post in the thread 

- `parent_ids` *(list)*: List

- `platform_specific`
