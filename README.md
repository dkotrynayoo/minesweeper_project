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
## Implemented Features 
모든 기능은 GitHub Issues와 Pull Requests를 통해 관리되었습니다. **Project Manager**가 이슈를 생성하고, 해당 기능을 구현했으며, 코드 리뷰를 완료한 후 Pull Request를 병합했습니다.


### Issue-1: 새로 시작기능 안내 추가
- 게임이 종료될 때, 결과(GAME OVER / GAME CLEAR)와 함께 화면에 재시작 안내 문구("R 키를 눌러 다시 시작")가 표시되도록 Game.draw 메서드를 업데이트했습니다.
- 결과 텍스트의 폰트 크기를 키워 게임 종료 결과가 더 눈에 띄도록 하고, 재시작 안내 문구는 상대적으로 작은 폰트로 표시하여 시각적 구분을 명확히 했습니다.
- 이제 게임이 종료되면 플레이어가 결과를 쉽게 확인하고 게임을 다시 시작하는 방법을 알 수 있습니다.
  
<img width="239" height="129" alt="image" src="https://github.com/user-attachments/assets/6b9f8839-c636-41e5-b527-d6671dfc5951" />
  
### Isuue-2: 타이머 기능 구현
- 타이머는 이제 플레이어가 처음 움직일 때 (self.started = True) 시작되며, 시작 시간(self.start_ticks_ms)을 기록합니다.
- 게임이 종료되면 종료 시간(self.end_ticks_ms)이 기록되어 타이머가 멈춥니다.
- 이를 통해 타이머는 게임 시작과 종료 사이에서만 업데이트되어, 실제 경과 시간을 정확하게 표시합니다.
  
<img width="207" height="75" alt="image" src="https://github.com/user-attachments/assets/e597e248-4af4-42af-ad8f-8dd6bfffe774" />


### Issue-3: 게임오버 시 잘못꽂은 깃발 표시
- Game 클래스의 draw_cell 및 draw(self) 메서드를 수정하여, 게임 종료 시 잘못된 깃발을 표시하도록 변경했습니다.
- 게임 오버 상태에서는 잘못된 깃발 위에 노란색 “X”가 표시되도록 렌더링 로직을 업데이트했습니다.
- 이제 게임이 끝나면 플레이어가 어떤 깃발이 잘못된지 직관적으로 확인할 수 있습니다.

<img width="249" height="193" alt="image" src="https://github.com/user-attachments/assets/2cec2fc3-cf47-408d-a66a-eba32b3ace02" />

### Issue-4 and 5: 힌트 기능 추가 + UI에 힌트 내용 추가
이 두 이슈는 서로의 로직에 의존하기 때문에 연결되어 있습니다.
수행한 작업:
   - H 키로 힌트 모드를 토글하고, 셀 클릭 시 올바르게 동작하도록 힌트 모드 로직을 구현했습니다.
   - 헤더를 업데이트하여 남은 힌트 수가 동적으로 표시되도록 했습니다.
   - 힌트를 사용하면 수가 감소하고, 힌트가 0이 되면 더 이상 사용할 수 없도록 처리했습니다.
   - 게임을 리셋하면 힌트 수가 올바르게 복구되도록 수정했습니다.

<img width="296" height="380" alt="image" src="https://github.com/user-attachments/assets/e39cd56d-ffdd-4572-939b-85629ceaa96e" />  <img width="398" height="296" alt="image" src="https://github.com/user-attachments/assets/8fd15d8d-d4c5-451f-be41-3b0d71683d9b" />


---
## License
이 프로젝트는 교육 목적으로 제작되었습니다.
상업적 라이선스는 적용되지 않습니다.
