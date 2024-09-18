# comparison-of-text-similarity
コサイン類似度、ジャッカード類似度、単語埋め込みを使った手法であるBERTとその類似度計算に最適化されたSentence-BERTを試した。

## Cosine Similarity (コサイン類似度)

文章をトークンに分割し、各単語の出現回数をベクトルとして表すことで2つのベクトル間のコサイン類似度を計算する。角度が小さいほど類似度が高い。

$$
\text{Cosine Similarity}(A, B) = \frac{A \cdot B}{\{||}A\{||} \  \{||}B\{||}}
$$


## Jaccard Similarity (ジャッカード類似度)
​
各文章を単語の集合に変換し、2つの集合の共通部分と和集合を計算して、共通部分の割合を求める。

$$
\text{Jaccard Similarity}(A, B) = \frac{|A \cap B|}{|A \cup B|}
$$


## Word Embedding（単語埋め込み）を使う (Sentence-BERT)

単語埋め込みを使い、文章を高次元の連続ベクトルとして表現する。それらのベクトル間の類似度を測定。


## BERT
今回はBERT (Bidirectional Encoder Representations from Transformers) の事前学習された深層学習モデルを使用した。文全体の意味を捉えたベクトル表現を得て、これを使って類似度 (コサイン類似度) で測定する。


# 結論

コサイン類似度およびジャッカード類似度はハードな測定方法だと感じたため、Word Emebedding を使ったほうがいい。計算効率とか考えるとSentence-BERTでいいと思う。
