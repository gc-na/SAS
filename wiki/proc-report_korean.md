<!--
Meta Description: # PROC REPORT: SAS에서 데이터 보고서 생성하기 ## 개요 `PROC REPORT`는 SAS에서 데이터를 요약하고 보고서를 생성하기 위한 강력한 프로시저입니다. 이 프로시저는 다양한 형식으로 데이터를 표시하고, 그룹화, 요약, 계산 및 사용자 정의 형식을 ...
Meta Keywords: proc, report, define, 보고서를, 있습니다
-->

# PROC REPORT: SAS에서 데이터 보고서 생성하기

## 개요
`PROC REPORT`는 SAS에서 데이터를 요약하고 보고서를 생성하기 위한 강력한 프로시저입니다. 이 프로시저는 다양한 형식으로 데이터를 표시하고, 그룹화, 요약, 계산 및 사용자 정의 형식을 지원하여 전문적인 보고서를 작성하는 데 유용합니다.

## 문서화
`PROC REPORT`는 데이터 세트를 기반으로 사용자 정의 보고서를 생성하는 데 사용됩니다. 이 프로시저는 다음과 같은 주요 기능을 제공합니다:

- **데이터 요약**: 여러 변수에 대해 그룹화하여 요약 통계를 계산할 수 있습니다.
- **형식 지정**: 사용자 정의 형식을 사용하여 출력 보고서의 가독성을 높일 수 있습니다.
- **계산된 열**: 계산된 열을 추가하여 데이터 분석을 더 깊이 있게 수행할 수 있습니다.
- **상호작용성**: 보고서 내에서 행과 열을 쉽게 조작하여 다양한 뷰를 생성할 수 있습니다.

### 사용법
`PROC REPORT`는 일반적으로 다음과 같은 구조로 사용됩니다:

```sas
PROC REPORT DATA=데이터셋명;
   COLUMNS 변수1 변수2 ...;
   DEFINE 변수1 / 옵션;
   DEFINE 변수2 / 옵션;
   ...
RUN;
```

각 옵션은 보고서의 형식 및 내용을 제어하는 데 사용됩니다. `DEFINE` 문을 통해 각 변수의 표시 방법을 설정할 수 있습니다.

## 예시
아래는 `PROC REPORT`의 기본 사용 예시입니다.

```sas
DATA example;
   INPUT Name $ Age Salary;
   DATALINES;
John 30 50000
Jane 25 60000
Doe 35 70000
;
RUN;

PROC REPORT DATA=example;
   COLUMNS Name Age Salary;
   DEFINE Name / DISPLAY;
   DEFINE Age / DISPLAY;
   DEFINE Salary / ANALYSIS MEAN;
RUN;
```

이 예시는 `Name`, `Age`, `Salary` 변수를 포함하는 보고서를 생성하며, `Salary`의 평균을 계산하여 표시합니다.

## 설명
`PROC REPORT`를 사용할 때 주의해야 할 몇 가지 사항은 다음과 같습니다:

- **변수 정의**: `DEFINE` 문에서 변수의 속성을 정확히 설정하지 않으면 예상치 못한 결과가 발생할 수 있습니다.
- **그룹화**: 그룹화 기능을 사용할 경우, 데이터 세트의 정렬 상태에 주의해야 합니다. 그룹화된 변수는 반드시 정렬된 상태여야 합니다.
- **출력 형식**: 출력 형식의 설정은 보고서의 가독성에 큰 영향을 미칩니다. 적절한 옵션을 선택하여 시각적으로 매력적인 보고서를 작성하세요.

## 한 줄 요약
`PROC REPORT`는 SAS에서 데이터를 요약하고 맞춤형 보고서를 생성하는 데 사용되는 강력한 프로시저입니다.