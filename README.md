## Translation Project

영-> 한 번역을 위한 Encoder-Decoder 모델

- 한국어 번역을 위해 Decoder에서 `monologg/koelectra-base-v3-discriminator`의 `token_embeddings`을 한국어 pretrained Subword Embedding으로 사용합니다.
- 영어 데이터를 위해 Encoder에서 `bert-base-uncased`의 pretrained model로 사용합니다.

###  Requirement

transformers  4.12.3
torch 1.9.0

### Preprocess

- 코퍼스를 어떤 토큰 단위로 쪼갤지 전처리 구간 필요
- subword 단위로 토큰화 작업 => SentencePiece Tokenizer

### Train

- Seq2Seq으로 학습
- 학습속도 개선 : Padding, Bucketing
