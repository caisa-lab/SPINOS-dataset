
<img src="SPINOS.jpeg" width="128"/> 

# SPINOS*: A Dataset of Subtle Polarity and Intensity Opinion Shifts



You will need Python>=3.8 and the following package to be installed in order to load the dataset:
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

- `s_against` (strongly against), `against` (weakly against), `stance_not_inferrable`, `favor` (weakly in favor), `s_favor` (strongly in favor) *(int)*: Count of how many times the non-expert annotators assigned the corresponding stance.

- `is_explicit` *(str)*: The stance is explicitly stated. Values = \['No', 'Yes'\].

- `is_sarcastic` *(str)*: The stance is sarcastic. Values = \['No', 'Yes'\].

- `timestamp` *(pandas Timestamp)*: Date and time when the post was posted.

- `toplevel_id` *(str)*: ID of the top-level post in the thread 

- `parent_ids` *(list)*: List of the parent posts' ids that where used for the annotation

- `platform_specific` *(dict)*: Dictionary with various attributes a post might have that are obtained from Reddit, namely: awards_, controversiality, media_only, num_comments, score, subreddit and title wherever they apply.

---

The dataset is introduced and analyzed in our paper: *Investigating User Radicalization: A Novel Dataset for Identifying Fine-Grained Temporal Shifts in Opinion*

---

* Fun fact: SPINOS in Greek (σπίνος) means chaffinch, which is our logo. Interestigly, this name bring together some of the authors of the paper, since the first author is Greek, the second author is an aspirant birdwatcher and the third author's surname means "bird" in German.
