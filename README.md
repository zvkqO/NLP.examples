# NLP.examples

NLP와 PyTorch 학습 내용을 날짜별로 정리한 실습 저장소입니다. 현재 저장소에는 서브워드 토크나이저 비교 실험과 PyTorch 기본/모델링 실습, Flickr8k 기반 이미지 캡셔닝 예제 자료가 포함되어 있습니다.

## 저장소 구성

```text
NLP.examples/
├─ 0625/
│  ├─ Subword_problem_1.ipynb
│  ├─ data/
│  │  ├─ raw/corpus.txt
│  │  └─ processed/corpus_documents.txt
│  └─ models/
│     ├─ huggingface/hf_bpe_tokenizer.json
│     └─ sentencepiece/
│        ├─ spm_nsmc_bpe.model
│        ├─ spm_nsmc_bpe.vocab
│        ├─ test_spm_8000.model
│        └─ test_spm_8000.vocab
├─ 0627/
│  ├─ Pytorch_Tutorial(Tensor).ipynb
│  ├─ Pytorch_Tutorial(Modeling).ipynb
│  ├─ Pytorch_problem_1.ipynb
│  ├─ hw2.ipynb
│  ├─ bottleneck_analysis.ipynb
│  └─ data/flickr8k/
│     ├─ Flickr8k.token.txt
│     └─ Flicker8k_Dataset/
└─ README.md
```

## 주요 내용

### 0625: Subword Tokenizer

`0625/Subword_problem_1.ipynb`는 NSMC(Naver Sentiment Movie Corpus) 데이터를 사용해 서브워드 토크나이저를 비교하는 실험 노트북입니다.

- NSMC 데이터 다운로드 및 전처리
- SentencePiece BPE 토크나이저 학습
- HuggingFace Tokenizers BPE 토크나이저 학습
- vocabulary, 토큰 빈도, 분절 결과 비교
- 단일 문장 및 전체 코퍼스 변환 속도 측정

학습에 사용한 corpus와 생성된 tokenizer/model 파일은 `0625/data/`, `0625/models/` 아래에 정리되어 있습니다.

### 0627: PyTorch and Flickr8k

`0627/` 폴더는 PyTorch 기초와 모델링 실습, 이미지 캡셔닝 과제 자료를 담고 있습니다.

- `Pytorch_Tutorial(Tensor).ipynb`: Tensor 생성, 연산, shape 조작 등 PyTorch 기본 문법
- `Pytorch_Tutorial(Modeling).ipynb`: 모델 정의, 학습 루프, 손실 함수, 최적화 흐름
- `Pytorch_problem_1.ipynb`: PyTorch 실습 문제 풀이
- `hw2.ipynb`: Flickr8k 데이터를 활용한 과제 노트북
- `bottleneck_analysis.ipynb`: 모델 또는 학습 과정의 병목 분석 노트북
- `data/flickr8k/`: caption token 파일과 샘플 이미지 데이터

## 실행 환경

Python 3.10 이상과 Jupyter Notebook 또는 VS Code Notebook 환경을 권장합니다.

주요 패키지는 다음과 같습니다.

```bash
pip install pandas requests sentencepiece tokenizers torch torchvision pillow matplotlib jupyter
```

사용하는 노트북에 따라 필요한 패키지가 조금씩 다를 수 있습니다. 패키지 누락 오류가 발생하면 현재 노트북 커널의 Python 경로를 확인한 뒤 해당 환경에 설치하세요.

```python
import sys
print(sys.executable)
```

## 사용 방법

1. 저장소를 클론합니다.

```bash
git clone https://github.com/zvkqO/NLP.examples.git
cd NLP.examples
```

2. 필요한 패키지를 설치합니다.

```bash
pip install pandas requests sentencepiece tokenizers torch torchvision pillow matplotlib jupyter
```

3. 원하는 날짜 폴더의 노트북을 실행합니다.

```bash
jupyter notebook
```

VS Code를 사용하는 경우 `.ipynb` 파일을 열고 적절한 Python 커널을 선택해 셀을 순서대로 실행하면 됩니다.

## 데이터 안내

- `0625/data/`에는 NSMC 기반 토크나이저 실험용 corpus 파일이 포함되어 있습니다.
- `0627/data/flickr8k/`에는 Flickr8k 실습을 위한 caption token 파일과 샘플 이미지가 포함되어 있습니다.
- 데이터의 저작권과 사용 조건은 각 원본 데이터셋의 라이선스 및 배포 조건을 따릅니다.

## 참고 자료

- NSMC: https://github.com/e9t/nsmc
- SentencePiece: https://github.com/google/sentencepiece
- HuggingFace Tokenizers: https://github.com/huggingface/tokenizers
- PyTorch: https://pytorch.org/
- Flickr8k Dataset: https://www.kaggle.com/datasets/adityajn105/flickr8k

## 저장소 정보

- GitHub: https://github.com/zvkqO
- Repository: https://github.com/zvkqO/NLP.examples
