# MINESWEEPER GAME
이 프로젝트는 클래식 지뢰찾기(Minesweeper) 게임을 구현한 것입니다.
지뢰찾기는 플레이어가 지뢰를 클릭하지 않고 보드 위의 모든 안전한 칸을 여는 것을 목표로 하는 1인용 퍼즐 게임입니다.
각 칸에는 지뢰가 있거나 안전한 칸일 수 있으며, 안전한 칸을 열면 주변 8칸에 있는 지뢰의 개수를 나타내는 숫자가 표시됩니다.

## Getting Started
이 안내는 개발 및 테스트를 위해 프로젝트를 로컬 환경에서 실행할 수 있도록 하는 방법을 설명합니다.

### Prerequisites
이 프로젝트를 실행하기 위해서는 다음 소프트웨어가 필요합니다:
-	Python 3.10 (recommended)
-	Pygame

### Installing
다음 단계를 따라 개발 환경을 설정하세요:
1. 저장소를 클론합니다
   
    `git clone <your github repository url>`

2. 프로젝트 디렉터리로 이동합니다

    `cd minesweeper`

3. 의존성을 설치합니다

    `pip install pygame`

## Running the Game
다음 명령어를 사용하여 게임을 실행하세요:

    python run.py

### Gameplay Demo
- 왼쪽 클릭: 칸 열기
- 오른쪽 클릭: 깃발 표시/해제
- 가운데 클릭(휠 클릭): 주변의 아직 열리지 않은 칸 강조 표시
- 첫 클릭 시 타이머 시작
- 지뢰 카운터는 깃발을 기준으로 남은 지뢰 수를 표시

## Running the Test
게임 로직과 기능의 정확성과 안정성을 검증하기 위해 수동 테스트를 진행했습니다.
다음과 같은 게임 플레이 시나리오를 수동으로 테스트했습니다:
- 첫 번째 칸을 클릭하면 게임이 정상적으로 시작됨
- 처음 클릭한 칸 및 그 주변 칸에는 지뢰가 배치되지 않음
- 지뢰를 열면 즉시 게임이 종료됨
- 모든 지뢰가 아닌 칸을 열었을 때 승리 조건이 정상적으로 발생함

## Built With
- Python 3.10
- Pygame – 게임 화면 렌더링 및 이벤트 처리
- Git & GitHub – 버전 관리 및 협업

## Contributing
이 프로젝트는 GitHub Issue → Pull Request → Code Review 워크플로를 따릅니다.
### Contribution Process
1. 저장소를 포크합니다
2. 기능 개발을 위한 브랜치를 생성합니다
3. Issue 설명을 기반으로 기능을 구현합니다
4. Issue 번호를 포함하여 커밋합니다:
   
   `git commit -m "<your commit message>(#<Issue 번호>)"`
5. Pull Request를 엽니다
6. 코드 리뷰에서 요청된 수정 사항을 반영합니다
7. Pull Request 승인 후 병합합니다
---
## Implemented Features (To be updated after feature merge)
다음 기능들은 GitHub Issue 및 Pull Request 워크플로를 통해 구현되었습니다.
각 기능은 Contributor가 구현했으며, 병합 전에 Project Manager의 리뷰를 거쳤습니다.

### Issue-1: Hint Button to Reveal One Safe Cell
### Isuue-2: High Score Save
### Issue-3: Difficulty Setting Feature
### Issue-4: Reveal All Connected Zero Cells
### Issue-5: Show Win / Lose Message

---
## License
이 프로젝트는 교육 목적으로 제작되었습니다.
상업적 라이선스는 적용되지 않습니다.
