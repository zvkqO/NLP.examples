# NLP.examples

서브워드 토크나이저 비교 실험 프로젝트입니다. 네이버 영화 리뷰(NSMC) 데이터를 사용하여 SentencePiece BPE와 HuggingFace Tokenizers BPE를 학습하고, 단어사전, 토큰 빈도, 변환 속도, 분절 결과를 비교합니다.

## 프로젝트 구성

```text
NLP.examples/
├─ README.md
├─ Subword_problem_1.ipynb
├─ data/
│  ├─ raw/
│  │  └─ corpus.txt
│  └─ processed/
│     └─ corpus_documents.txt
└─ models/
   ├─ huggingface/
   │  └─ hf_bpe_tokenizer.json
   └─ sentencepiece/
      ├─ spm_nsmc_bpe.model
      ├─ spm_nsmc_bpe.vocab
      ├─ test_spm_8000.model
      └─ test_spm_8000.vocab
```

- `Subword_problem_1.ipynb`: 전체 실험 노트북
- `data/raw/corpus.txt`: NSMC 원본 학습 데이터
- `data/processed/corpus_documents.txt`: `document` 컬럼만 추출한 정제 데이터
- `models/sentencepiece/`: SentencePiece 학습 결과
- `models/huggingface/`: HuggingFace Tokenizers 학습 결과

## 프로젝트 프로그램 설치방법

Python 3.10 이상 환경을 권장합니다.

```bash
pip install pandas requests sentencepiece tokenizers ipython jupyter
```

Jupyter Notebook 또는 VS Code의 Notebook 환경에서 `Subword_problem_1.ipynb`를 열어 실행할 수 있습니다.

## 프로젝트 프로그램 사용법

1. 저장소를 클론합니다.

```bash
git clone https://github.com/zvkqO/NLP.examples.git
cd NLP.examples
```

2. 필요한 패키지를 설치합니다.

```bash
pip install pandas requests sentencepiece tokenizers ipython jupyter
```

3. `Subword_problem_1.ipynb`를 실행합니다.

노트북은 다음 순서로 구성되어 있습니다.

- 데이터 다운로드 및 정제
- SentencePiece BPE 단어사전 구축
- HuggingFace Tokenizers BPE 단어사전 구축
- 상위 vocab 및 실제 분절 토큰 빈도 분석
- 단일 문장/전체 코퍼스 변환 속도 측정
- 추가 예문 분절 및 통계 비교
- 사용성과 장단점 분석

이미 `data/`와 `models/` 폴더에 데이터와 학습 결과가 포함되어 있으므로, 전체 재학습 없이 결과를 확인할 수 있습니다. 재실행하면 기존 파일을 기준으로 다시 정제 및 학습 결과가 생성될 수 있습니다.

## 저작권 및 사용권 정보

이 저장소의 과제 코드와 문서는 별도 라이선스가 명시되지 않은 상태입니다. 사용, 배포, 수정 권한이 필요한 경우 저장소 소유자에게 확인해야 합니다.

데이터는 NSMC(Naver Sentiment Movie Corpus)를 사용합니다. 원본 데이터의 저작권과 사용 조건은 NSMC 저장소의 안내를 따릅니다.

## 프로그래머 정보

- GitHub: [zvkqO](https://github.com/zvkqO)
- Repository: [zvkqO/NLP.examples](https://github.com/zvkqO/NLP.examples)

## 버그 및 디버그

자주 발생할 수 있는 문제는 다음과 같습니다.

- `ModuleNotFoundError`: 현재 노트북 커널에 필요한 패키지가 설치되어 있지 않은 경우입니다. 노트북에서 `import sys; sys.executable`로 커널 경로를 확인한 뒤 해당 Python에 패키지를 설치합니다.
- `sentencepiece` 설치 실패: Python 버전 또는 운영체제 환경에 맞는 wheel이 없는 경우 발생할 수 있습니다. Python 3.10 이상 안정 버전을 권장합니다.
- GitHub 다운로드 실패: 네트워크 또는 프록시 문제일 수 있습니다. 이미 포함된 `data/raw/corpus.txt`를 사용하면 재다운로드 없이 실험할 수 있습니다.
- Windows 콘솔 한글/특수문자 깨짐: 터미널 인코딩 문제일 수 있습니다. Jupyter Notebook 화면에서는 `▁` 같은 토큰 표시가 정상적으로 보입니다.

버그를 발견하면 재현 절차, 오류 메시지, 사용한 Python 버전, 실행 환경을 함께 기록하는 것이 좋습니다.

## 참고 및 출처

- NSMC 데이터: https://github.com/e9t/nsmc
- NSMC raw train file: https://raw.githubusercontent.com/e9t/nsmc/master/ratings_train.txt
- SentencePiece: https://github.com/google/sentencepiece
- HuggingFace Tokenizers: https://github.com/huggingface/tokenizers
- pandas: https://pandas.pydata.org/

## 버전 및 업데이트 정보

- `v0.1.0`: 초기 과제 노트북 작성
  - NSMC 데이터 정제
  - SentencePiece/HuggingFace BPE 학습
  - vocab 및 토큰 빈도 비교
  - 단일 문장/전체 코퍼스 변환 속도 비교
  - 추가 실험 및 결과 해석 작성

