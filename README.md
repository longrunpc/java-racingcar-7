# 자동차 경주

---
## 기능 요구 사항

초간단 자동차 경주 게임을 구현한다.

- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
- 우승자가 여러 명일 경우 쉼표(,)를 이용하여 구분한다.
- 사용자가 잘못된 값을 입력할 경우 `IllegalArgumentException`을 발생시킨 후 애플리케이션은 종료되어야 한다.

---
## 입출력 요구 사항

**입력**
- 경주할 자동차 이름(이름은 쉼표(,) 기준으로 구분)
```pobi,woni,jun```
- 시도할 횟수
```5```
**출력**
- 차수별 실행 결과
```결과 : 6```
- 단독 우승자 안내 문구
```최종 우승자 : pobi```
- 공동 우승자 안내 문구 
```최종 우승자 : pobi, jun```
  **실행 결과 예시**
```
경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
pobi,woni,jun
시도할 횟수는 몇 회인가요?
5

실행 결과
pobi : -
woni : 
jun : -

pobi : --
woni : -
jun : --

pobi : ---
woni : --
jun : ---

pobi : ----
woni : ---
jun : ----

pobi : -----
woni : ----
jun : -----

최종 우승자 : pobi, jun
```

---
## 구현 기능 목록

---
### 1. **Model**

---
#### 1.1. **Car**
- [x] 자동차 객체의 이름과 위치를 저장하고 관리하는 모델
- [x] 이름 유효성 확인 기능
- [x] 이름 반환 기능
- [x] 위치 반환 기능
- [x] `MoveStrategy`를  통해 이동 여부 결정 후, 위치 이동 기능
#### 1.2  **RacingGame**
- [x] 입력받은 자동차 이름 리스트를 기반으로 `Car` 객체 리스트 생성
- [x] `MoveStrategy` 를 기반으로 각각의 자동차가 이동하는 라운드 진행
- [x] 자동차 리스트를 반환 하는 기능
- [x] 우승자를 결정하고 반환하는 기능
#### 1.3  **MoveStrategy**
- [x] `camp.nextstep.edu.missionutils.Randoms`를 사용하여 자동차가 이동할수 있는지 여부 체크
---
### 2. **View**

---
#### 2.1. **InputView (입력 기능)**
- [ ] 쉼표(,)로 구분된 자동차 이름 목록을 입력받는다.
- [ ] 사용자가 게임의 총 시도 횟수를 입력할 수 있도록 한다.
- [ ] 이름이 1~5자 이내인지, 시도 횟수가 1 이상인지 확인하고, 잘못된 입력 시 예외를 발생시킨다.
#### 2.2. **OutputView (출력 기능)**
- [ ] 게임 시작 메시지를 출력한다.
- [ ] 각 라운드가 끝날 때 자동차의 현재 위치를 출력한다.
- [ ] 게임 종료 후 우승자를 출력한다. 우승자가 여러 명일 경우 쉼표로 구분하여 출력한다.
---
### 3. **Controller**

---
#### 3.1 **RacingGameController**
- [ ] 사용자 입력 처리: InputView를 통해 사용자로부터 자동차 이름과 시도 횟수를 입력받는다.
- [ ] 게임 진행 관리: RacingGame을 초기화하고 각 라운드를 진행한다.
- [ ] 결과 출력: 게임이 끝난 후 OutputView를 통해 최종 결과(우승자)를 출력한다.
---
