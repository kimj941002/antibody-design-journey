# Antibody Design Journey

항체 설계·평가 소프트웨어를 직접 구현하며 Python, 계산생물학, 딥러닝을 배우는 프로젝트입니다. 갤럭스 In silico 신약 설계 연구원 직무를 목표로, 학습 기록을 재현 가능한 개발 결과물로 발전시킵니다.

## 현재 상태

- 기존 Python 학습 노트북과 `1N8Z.pdb` 원본을 보존했습니다.
- 기능별 개발 폴더와 데이터·보고서 관리 기준을 마련했습니다.
- **구조 분석 프로그램, ProteinMPNN/RFantibody 연동, PyTorch 모델 학습은 아직 구현하지 않았습니다.** 아래 기능 폴더의 README는 개발 계획입니다.
- 노트북에는 연습 중 발생한 오류와 예시 점수가 포함되어 있습니다. 실제 모델의 예측·성능 결과가 아닙니다.

## 프로젝트 구조

```text
antibody-design-journey/         # 이 컴퓨터에서는 /home/kjk/work
├── structure_analysis/         # PDB/mmCIF, chain, CDR, epitope, 거리 분석
├── sequence_design/            # ProteinMPNN 실행 및 서열 결과 처리
├── model_training/             # 공개 binder 데이터로 PyTorch 모델 학습
├── design_pipeline/            # RFantibody 실행 자동화 및 통합
├── evaluation/                 # RMSD, 접촉 잔기, AUROC/AUPRC 등 평가
├── benchmarks/                 # 설정별 성능·시간·메모리 비교
├── tests/                      # 구현 기능의 검증 코드
├── reports/                    # 실험·논문 분석 보고서
├── notebooks/
│   └── foundations/Phase2.ipynb # 기존 Python 기초 학습 기록
├── data/
│   ├── raw/1N8Z.pdb            # 기존 구조 원본
│   └── processed/              # 가공 데이터 (Git 제외)
├── scripts/                    # 공통 실행·다운로드 스크립트
├── results/                    # 실행 산출물 (Git 제외)
├── environments/               # 이전 환경 명세 보존
├── environment.yml             # 새 CPU 기초 실습 환경
├── requirements.txt
└── .gitignore
```

## Ubuntu에서 시작하기

기존 작업 경로와 Git 원격 주소는 유지합니다.

```bash
cd /home/kjk/work
```

새 환경은 다음 중 **한 방법만** 선택하세요. 기존 `bio` 환경은 변경하지 않습니다.

### Conda 사용

```bash
conda env create -f environment.yml
conda activate antibody-study
python -c "import Bio, numpy; print('Installation OK')"
jupyter lab
```

### Python venv 사용

Python 3.11 이상이 준비된 경우:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m pip install jupyterlab
python -c "import Bio, numpy; print('Installation OK')"
jupyter lab
```

`notebooks/foundations/Phase2.ipynb`를 열어 기존 학습을 이어갈 수 있습니다. 이 노트북은 오류를 포함한 원본 학습 기록이며 전체 셀 실행 성공을 보장하지 않습니다. 파일 경로를 사용하는 새 코드는 저장소 루트를 기준으로 작성합니다.

현재 의존성은 첫 구조 분석 수업용입니다. GPU 모델 환경은 모델별로 분리하고, PyTorch/CUDA는 GPU·드라이버와 모델의 요구사항을 확인한 뒤 설치합니다. 버전을 고정한 재현 환경은 첫 실행 검증 후 기록합니다.

## 다음 구현 목표

1. `structure_analysis/`에 PDB를 읽고 chain별 잔기 수를 출력하는 코드를 직접 작성합니다.
2. 원자 간 거리와 항체–항원 접촉 잔기 분석을 추가합니다.
3. 단위 검증과 실행 예시를 작성하고, 실제 결과를 `reports/`에 기록합니다.
4. ProteinMPNN → 공개 binder 데이터 학습 → RFantibody 통합으로 확장합니다.

[데이터 출처와 관리](data/README.md)

## GitHub에 기록하기

```bash
cd /home/kjk/work
git status
git add structure_analysis tests reports README.md
git diff --cached
git commit -m "Add chain analysis and record verified results"
git push origin main
```

위 명령은 실제 작업 후 변경된 경로에 맞게 사용하세요. 대형 데이터, 모델 가중치, 개인 설정은 커밋하지 않습니다. 외부 모델 활용 부분과 직접 구현한 부분을 구분하고, 측정하지 않은 성능을 기재하지 않습니다.
