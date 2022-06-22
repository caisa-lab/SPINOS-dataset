
<img src="SPINOS.jpeg" width="128"/> 

# SPINOS[^note]: A Dataset of <ins>S</ins>ubtle <ins>P</ins>olarity and <ins>IN</ins>tensity <ins>O</ins>pinion <ins>S</ins>hifts
You can find <a href="https://rawcdn.githack.com/caisa-lab/SPINOS-dataset/8adb8d3100632044378c44d5433b8226b306be26/annotation_template/annotation_template_example_abortion.html" target="_blank"> here</a> an example of the annotation template for abortion. 

The dataset is introduced and analyzed in our<a href="https://arxiv.org/abs/2204.10190" target="_blank"> paper</a>: *Investigating User Radicalization: A Novel Dataset for Identifying Fine-Grained Temporal Shifts in Opinion*, Flora Sakketou, Allison Lahnala, Liane Vogel and Lucie Flek

Read <a href="https://caisa-lab.github.io/2022/04/08/LREC-spinos.html" target="_blank"> here</a> a blog post about our paper.


You will need Python>=3.8 and the following package to be installed in order to load the dataset:
```
pip install pandas==1.4.1
```

You can read the data with:
```
import pandas as pd

data = pd.read_pickle('SPINOS_official_dataset.pkl')
context_posts = pd.read_pickle('SPINOS_context_for_annotators.pkl')
```
The index of the rows corresponds to the ids of the posts in the Reddit API

The dataframe contains the following columns:

- `author_id` *(str)*: Which user has posted this particular post. *Note:* The usernames are anonymous.

- `title` *(str)*: The title of the post, if it exists.

- `content` *(str)*: The content of the post, if it exists.

- `annotation` *(str)*: Majority vote of the non-expert annotators.

- `topic` *(str)*: The topic this post is about. Possible values: 'abortion' 'feminism' 'brexit' 'veganism' 'guns' 'nuclear-energy'
 'capitalism' 'climate-change'

 - `subreddit` *(str)*: The subreddit this post was posted on.

- `is_sarcastic` *(str)*: The stance is sarcastic. Values = \['', 'No', 'Yes'\].

- `is_unsure` *(str)*: How many annotators stated that they were unsure of the annotation. Values = \['', 'No', '1/3', '2/3'\].

- `is_explicit` *(str)*: The stance is explicitly stated. Values = \['No', 'Yes'\].

- `top_level_post`:  How many annotators requested to read the top-level post in order to do the annotation. Values = \['No', '1', '2', '3'\]

- `top_level_post_id` *(str)*: ID of the top-level post in the thread 

- `parents`:  How many annotators requested to read the parent posts in order to do the annotation. Values = \['No', '1', '2', '3'\]

- `parent_ids` *(list)*: List of the parent posts' ids that where used for the annotation

- `timestamp` *(pandas Timestamp)*: Date and time when the post was posted.

---



[^note]: Fun fact: SPINOS in Greek (σπίνος) means chaffinch, which is our logo. Interestigly, this name brings together some of the authors of the paper, since the first author is Greek, the second author is an aspirant birdwatcher and the third author's surname means "bird" in German.
