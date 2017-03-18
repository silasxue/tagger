# Tagger
A Joint Chinese segmentation and POS tagger based on bidirectional GRU-CRF

To reproduce the results reported in the paper:

# Single
python tagger.py train -p ud1 -t train.txt -d dev.txt -wv -crf 1 -cp -tg BIES -ng 3 -rd -iter 30 -lr 0.1 -ld 0.05 -gru -op adagrad -m gru_full_ud1 -emb Embeddings/glove.txt

python tagger.py test -p ud1 -e test.txt -m gru_full_ud1 -emb Embeddings/glove.txt

# Ensemble

python tagger.py train -p ud1 -t train.txt -d dev.txt -wv -crf 1 -cp -tg BIES -ng 3 -rd -iter 30 -lr 0.1 -ld 0.05 -gru -op adagrad -m gru_full_ud1_1 -emb Embeddings/glove.txt

python tagger.py train -p ud1 -t train.txt -d dev.txt -wv -crf 1 -cp -tg BIES -ng 3 -rd -iter 30 -lr 0.1 -ld 0.05 -gru -op adagrad -m gru_full_ud1_2 -emb Embeddings/glove.txt

python tagger.py train -p ud1 -t train.txt -d dev.txt -wv -crf 1 -cp -tg BIES -ng 3 -rd -iter 30 -lr 0.1 -ld 0.05 -gru -op adagrad -m gru_full_ud1_3 -emb Embeddings/glove.txt

python tagger.py train -p ud1 -t train.txt -d dev.txt -wv -crf 1 -cp -tg BIES -ng 3 -rd -iter 30 -lr 0.1 -ld 0.05 -gru -op adagrad -m gru_full_ud1_4 -emb Embeddings/glove.txt

python tagger.py test -ens -p ud1 -e test.txt -m gru_full_ud1 -emb Embeddings/glove.txt
