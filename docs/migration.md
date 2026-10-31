# 저장소 구조 개편 — 2026-10-31

저장소 이름 `antibody-design-journey`, 로컬 루트 `/home/kjk/work`, 원격 주소와 기존 Git 커밋 이력은 유지합니다. 홈 디렉터리 전체를 저장소로 만들거나 Conda·CUDA 설치 경로를 이동하지 않습니다.

| 이전 경로 | 새 경로 | 처리 |
| --- | --- | --- |
| `phase2-python/notebooks/Phase2.ipynb` | `notebooks/foundations/Phase2.ipynb` | 내용·출력 그대로 보존 |
| `phase2-python/data/1N8Z.pdb` | `data/raw/1N8Z.pdb` | 원본 그대로 보존 |
| `phase2-python/environment.yml` | `environments/legacy-bio.yml` | 기존 명세 보존 |
| `phase2-python/.gitignore` | `.gitignore` | 루트 기준으로 통합·확장 |
| `phase2-python/scripts/.gitkeep` | `scripts/README.md` | 빈 폴더 표식을 설명 문서로 대체 |
| `phase2-python/results/.gitkeep` | `results/README.md` | 빈 폴더 표식을 관리 문서로 대체 |

기존 `scripts/`, `results/`, `output/`에는 실제 파일이 없었습니다. 로컬 전체 사본은 `/home/kjk/archive/antibody-design-journey/` 아래 개편 전 백업에 있습니다. 로컬 Git 브랜치 `backup/before-project-restructure-20261031`도 개편 전 커밋을 가리킵니다.

이전 노트북 탭은 새 경로에서 다시 열어 주세요. 새 작업은 `cd /home/kjk/work`에서 시작합니다. 이번 변경은 폴더 구조와 안내 문서 개편이며, 새 AI 모델 실행·학습 실적을 추가한 것이 아닙니다.
