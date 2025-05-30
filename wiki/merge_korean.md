<!--
Meta Description: # SAS의 MERGE 명령어: 데이터셋 병합 방법 ## 개요 SAS에서 MERGE 명령어는 두 개 이상의 데이터셋을 공통 변수를 기준으로 병합하는 데 사용됩니다. 이 기능은 데이터 분석 및 처리에 있어 매우 유용합니다. ## 문서화 MERGE 명령어는 SAS에서 여러...
Meta Keywords: merge, 데이터셋을, 데이터셋의, 있습니다, data
-->

# SAS의 MERGE 명령어: 데이터셋 병합 방법

## 개요
SAS에서 MERGE 명령어는 두 개 이상의 데이터셋을 공통 변수를 기준으로 병합하는 데 사용됩니다. 이 기능은 데이터 분석 및 처리에 있어 매우 유용합니다.

## 문서화
MERGE 명령어는 SAS에서 여러 데이터셋을 결합하여 하나의 데이터셋으로 만드는 방법을 제공합니다. 이 과정에서 공통 변수(키)를 사용하여 각 데이터셋의 데이터를 결합합니다. MERGE를 사용하면 데이터셋 간의 관계를 유지하면서 필요한 정보를 통합할 수 있습니다.

### 사용법
MERGE 명령어의 기본 구문은 다음과 같습니다:

```sas
DATA 합쳐진_데이터셋;
    MERGE 데이터셋1 데이터셋2;
    BY 공통변수;
RUN;
```

- `DATA`는 새로 생성할 데이터셋의 이름을 지정합니다.
- `MERGE`는 결합할 데이터셋을 나열합니다.
- `BY`는 공통 변수를 지정하며, 해당 변수를 기준으로 데이터셋을 병합합니다.

### 세부사항
- 병합할 데이터셋은 미리 정렬되어 있어야 합니다. `BY` 절의 변수로 정렬되어 있지 않으면 오류가 발생합니다.
- 중복된 키 값이 있는 경우, SAS는 첫 번째 데이터셋의 값을 사용합니다.
- `IN=` 옵션을 사용하여 각 데이터셋에서 관측치의 존재 여부를 추적할 수 있습니다.

## 예제
다음은 두 개의 데이터셋을 병합하는 간단한 예제입니다.

```sas
DATA 직원;
    INPUT 직원ID $ 이름 $;
    DATALINES;
    1 홍길동
    2 김철수
    3 이영희
    ;
RUN;

DATA 급여;
    INPUT 직원ID $ 급여;
    DATALINES;
    1 50000
    2 60000
    ;
RUN;

DATA 합쳐진_데이터셋;
    MERGE 직원 급여;
    BY 직원ID;
RUN;
```

위의 코드에서 `직원` 데이터셋과 `급여` 데이터셋을 `직원ID`를 기준으로 병합하여 `합쳐진_데이터셋`을 생성합니다.

## 설명
MERGE 명령어 사용 시 주의해야 할 점은 다음과 같습니다:
- **정렬**: 병합할 데이터셋이 `BY` 절의 변수로 정렬되어 있어야 하며, 정렬되지 않은 경우에는 예기치 않은 결과가 발생할 수 있습니다.
- **중복 키**: 중복된 키 값이 있는 경우, 병합된 데이터셋에서 첫 번째 데이터셋의 값이 우선 적용됩니다. 이로 인해 데이터 손실이 발생할 수 있으므로 주의해야 합니다.
- **IN= 옵션**: 이 옵션을 사용하면 각 데이터셋에서 관측치의 존재 여부를 쉽게 추적할 수 있습니다. 이를 통해 데이터셋의 일관성을 유지할 수 있습니다.

## 한 줄 요약
SAS의 MERGE 명령어는 공통 변수를 기준으로 여러 데이터셋을 병합하여 새로운 데이터셋을 생성하는 기능입니다.