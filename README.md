# **Table of contents**
- [Motivation](https://github.com/snakers4/emoji-sentiment-dataset/tree/master#downloads)
- [Dataset](https://github.com/snakers4/emoji-sentiment-dataset/tree/master#dataset)
- [Downloads](https://github.com/snakers4/emoji-sentiment-dataset/tree/master#downloads)
- [Methodology](https://github.com/snakers4/emoji-sentiment-dataset/tree/master#methodology)
- [License](https://github.com/snakers4/emoji-sentiment-dataset/tree/master#license)


# **Motivation**

Following the success of DeepMoji and TorchMoji ([1](https://arxiv.org/abs/1708.00524), [2](https://github.com/huggingface/torchMoji)), we would like to leverage Twitter as an open source of self-annotated data to create a balanced multi-language "in-the-wild" sentiment dataset to test the quality of various NLP models and/or word/sub-word tokenization techniques.

# **Dataset**

| Name                    | Sample size | Word vocab | Ngram vocab | Family        | Alphabet        | Speakers L1, m |
|-------------------------|-------------|------------|-------------|---------------|-----------------|----------------|
| Korean (ko)             | 198,561     | 516,021    | 1,862,406   | Koreanic      | Hangul          | 77             |
| Arabic (ar)             | 199,993     | 287,578    | 1,428,286   | Afro-Asiatic  | Arabic alphabet | 300            |
| Turkish (tr)            | 199,993     | 203,657    | 687,284     | Turkic        | Latin           | 80             |
| Russian (ru)            | 241,117     | 172,653    | 812,315     | Indo-European | Cyrillic        | 150            |
| Spanish, Castilian (es) | 299,995     | 117,629    | 498,977     | Indo-European | Latin           | 480            |
| Indonesian (id)         | 199,357     | 100,272    | 458,047     | Austronesian  | Latin           | 43             |
| French (fr)             | 299,995     | 99,631     | 476,360     | Indo-European | Latin           | 77             |
| German (de)             | 184,109     | 99,213     | 516,005     | Indo-European | Latin           | 90             |
| English (en)            | 299,995     | 95,666     | 523,046     | Indo-European | Latin           | 400            |
| Italian (it)            | 210,703     | 95,604     | 398,091     | Indo-European | Latin           | 69             |
| Thai (th)               | 349,995     | 73,425     | 558,911     | Tai–Kadai     | Thai script     | 30             |

# **Downloads**
- Curated/pre-processed/balanced [dataset](https://emoji-sentiment.ams3.digitaloceanspaces.com/fin_tweets.feather) - 540MB;
- Raw [dataset](https://emoji-sentiment.ams3.digitaloceanspaces.com/twitter_proc_full.feather) - 2.4 GB;


# **Methodology**
- Download and [process](https://github.com/snakers4/emoji_sentiment/blob/master/src/process_tweets.py) tweet archives from [archive team](https://archive.org/details/twitterstream);
- [Filter](https://github.com/snakers4/emoji_sentiment/blob/master/src/utils/text_utils.py#L207) Twitter-specific content (re-tweets, hashtags, citations, etc);
- Predict language with [FastText](https://fasttext.cc/docs/en/language-identification.html) and select items with high confidence (80-90%+);
- [Select](https://github.com/snakers4/emoji_sentiment/blob/master/src/utils/text_utils.py#L300) tweets that:
  - Contain one of 64 emojis used in TorchMoji / DeepMoji;
  - Do not contain other emojis;
  - Have only one block of consecutive emojis;
  - There is only one type of emoji per tweet;
- Dataset pre-processing and balancing;
- TODO

# **License**
Dual license, cc-by-nc and commercial usage available after agreement with dataset authors.
