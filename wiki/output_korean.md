<!--
Meta Description: # OUTPUT: SAS에서 데이터 출력의 모든 것 ## 개요 SAS에서 "OUTPUT"은 데이터 세트를 생성하거나 수정하는 데 사용되는 중요한 명령어입니다. OUTPUT 문을 통해 특정 조건을 만족하는 데이터 레코드를 선택하고, 새로운 데이터 세트를 생성할 수 있습니...
Meta Keywords: 데이터, output, 세트를, 새로운, 데이터를
-->

# OUTPUT: SAS에서 데이터 출력의 모든 것

## 개요
SAS에서 "OUTPUT"은 데이터 세트를 생성하거나 수정하는 데 사용되는 중요한 명령어입니다. OUTPUT 문을 통해 특정 조건을 만족하는 데이터 레코드를 선택하고, 새로운 데이터 세트를 생성할 수 있습니다.

## 문서화

### 목적
OUTPUT 문은 SAS 데이터 단계에서 데이터를 출력하고 조작할 수 있는 기능을 제공합니다. 이를 통해 데이터 분석, 보고서 작성, 데이터 변환 등 다양한 작업을 수행할 수 있습니다.

### 사용법
OUTPUT 문은 주로 DATA 단계 내에서 사용됩니다. 기본적인 형태는 다음과 같습니다:

```sas
DATA new_dataset;
    SET old_dataset;
    IF condition THEN OUTPUT;
RUN;
```

- `new_dataset`: 생성할 새로운 데이터 세트의 이름입니다.
- `old_dataset`: 기존 데이터 세트의 이름입니다.
- `condition`: 출력할 데이터를 결정하는 조건식입니다.

### 세부 사항
- OUTPUT 문은 여러 번 사용할 수 있으며, 각 호출 시마다 데이터 레코드가 출력됩니다.
- OUTPUT 문은 특정 조건이 충족될 때만 데이터를 출력하며, IF 문과 함께 사용되는 경우가 많습니다.
- OUTPUT 문이 호출되지 않으면 해당 데이터 레코드는 생성되지 않습니다.
- OUTPUT 문은 여러 데이터 세트를 동시에 생성할 수 있습니다.

## 예제

### 기본 사용 예제
다음은 특정 조건을 만족하는 데이터를 새로운 데이터 세트에 출력하는 간단한 예제입니다.

```sas
DATA high_scores;
    SET scores;
    IF score > 90 THEN OUTPUT;
RUN;
```
위 코드는 `scores` 데이터 세트에서 `score`가 90을 초과하는 모든 레코드를 `high_scores`라는 새로운 데이터 세트에 출력합니다.

### 여러 OUTPUT 사용 예제
다음은 두 개의 서로 다른 데이터 세트를 출력하는 예제입니다.

```sas
DATA categorized_scores;
    SET scores;
    IF score < 60 THEN OUTPUT low_scores;
    ELSE IF score >= 60 AND score < 90 THEN OUTPUT medium_scores;
    ELSE OUTPUT high_scores;
RUN;
```
여기서 `low_scores`, `medium_scores`, 및 `high_scores`라는 세 개의 데이터 세트가 각각의 조건에 따라 생성됩니다.

## 설명
OUTPUT 문을 사용할 때 주의해야 할 점은 조건식이 항상 TRUE인 경우, 무한히 데이터를 출력할 수 있다는 것입니다. 또한, OUTPUT 문이 호출되지 않으면 데이터 세트가 비어 있게 되므로, 항상 조건문을 잘 설정해야 합니다.

또한, OUTPUT 문을 사용할 때 명확한 데이터 흐름을 유지하는 것이 중요합니다. 복잡한 조건을 사용할 경우, 디버깅이 어려울 수 있으므로 코드를 잘 구조화하고 주석을 추가하는 것이 좋습니다.

## 한 줄 요약
SAS의 OUTPUT 문은 특정 조건에 따라 데이터 레코드를 선택하고 새로운 데이터 세트를 생성하는 데 사용됩니다.