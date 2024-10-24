# javascript-racingcar-precourse

<br>

## 0. 기능 요구사항

- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.

- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
- 우승자가 여러 명일 경우 쉼표(,)를 이용하여 구분한다.
- 사용자가 잘못된 값을 입력할 경우 "[ERROR]"로 시작하는 메시지와 함께 Error를 발생시킨 후 애플리케이션은 종료되어야 한다.

<br>

## 1. 기능 요구사항 분석

1. 경주할 자동차 이름 입력받기(쉼표 기준으로 구분)

   - 자동차 이름이 중복될 경우 ERROR
   - 자동차 이름 내에 공백이 있을 경우 공백 제거
     > EX. qq qq, w w -> qqqq와 ww가 된다
   - 공백 제거된 자동차 이름의 길이가 5자 초과 인지 check(공백은 자동차 이름 길이에 포함 ❌)
     > EX. qq qqqq, w w w -> qqqqqq와 www가 되고  
     >  첫번째 차가 5자를 초과하므로 유효한 자동차 이름이 아님
   - 구분자( , ) 없이 한대만 입력됐다면 ERROR
     > EX. qqq ( ❌ )
   - 구분자( , )가 입력된다면 최소 2대 이상의 자동차 이름을 입력해야한다.
     > EX. qqq,www ( ⭕ )  
     > EX. qqq, ( ❌ )

2. 시도할 횟수 입력받기
   - 자연수만 입력 가능
     > EX. 4.0 ( ⭕ ), 3 ( ⭕ )  
     > EX. 1.2 ( ❌ ), 0 ( ❌ ), a ( ❌ )
   - 지수표기법이나 n진수는 상관 없음
     > EX. 0x1F = 31 ( ⭕ )  
     > EX. 10e1 = 100 ( ⭕ )
3. 시도횟수만큼 loop 동작.
4. random number가 4이상인 경우 전진하며 " - " 가 하나씩 추가된다.
5. 마지막으로 " - "의 길이가 가장 긴 사람이 우승하며 우승자는 여러명일 수 있다.
   - 만약 모든 자동차가 게임이 끝날때까지 전진을 아예 안했다면 ERROR

<br>

## 2. 폴더 구조

/src  
├── App.js  
├── index.js  
├── Validator.js ⬅️입력 검증을 처리하는 클래스  
├── Input.js ⬅️사용자로부터 입력을 처리하는 클래스  
├── Race.js ⬅️경주 로직을 처리하는 클래스  
└── Constants.js ⬅️상수들 정의하는 클래스
