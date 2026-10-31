# Antibody Design Journey

항체 설계·평가 소프트웨어를 직접 구현하며 Python, 계산생물학, 딥러닝을 배우는 프로젝트

## 프로젝트 구조

```text
antibody-design-journey/        
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
├── environments/     
├── environment.yml             
├── requirements.txt
└── .gitignore