<!--
Meta Description: # PROC MEANS: SAS에서 데이터 요약 통계 계산하기 ## 개요 PROC MEANS는 SAS에서 데이터 세트의 기술 통계를 계산하는 데 사용되는 절차입니다. 이 명령어는 평균, 표준 편차, 최소값, 최대값 등 다양한 통계량을 손쉽게 구할 수 있게 해줍니다. #...
Meta Keywords: proc, 있습니다, 통계를, data, means
-->

# PROC MEANS: SAS에서 데이터 요약 통계 계산하기

## 개요
PROC MEANS는 SAS에서 데이터 세트의 기술 통계를 계산하는 데 사용되는 절차입니다. 이 명령어는 평균, 표준 편차, 최소값, 최대값 등 다양한 통계량을 손쉽게 구할 수 있게 해줍니다.

## 문서화
### 목적
PROC MEANS는 데이터 분석 과정에서 요약 통계를 제공하여, 데이터의 일반적인 경향을 파악하고, 데이터의 분포 및 변동성을 이해하는 데 도움을 줍니다.

### 사용법
PROC MEANS 구문은 다음과 같은 기본 형식을 가집니다:

```sas
PROC MEANS DATA=<데이터셋> <옵션>;
   VAR <변수명>;
RUN;
```

- **DATA**: 분석할 데이터셋의 이름을 지정합니다.
- **VAR**: 통계를 계산할 변수명을 리스트합니다.
- **옵션**: 계산할 통계량을 지정하는 다양한 옵션을 추가할 수 있습니다. 예를 들어, `N`, `MEAN`, `STD`, `MIN`, `MAX` 등을 사용할 수 있습니다.

### 자세한 설명
PROC MEANS는 다양한 통계량을 계산할 수 있으며, 기본적으로는 평균과 표준 편차를 포함합니다. 추가 옵션을 통해 원하는 통계량을 선택할 수 있으며, 결과는 출력 데이터셋으로 저장할 수 있습니다. 이 절차는 대규모 데이터셋에서도 효율적으로 작동합니다.

## 예제
### 기본 사용 예제
```sas
DATA sample;
    INPUT score;
    DATALINES;
    78
    82
    88
    90
    95
    ;
RUN;

PROC MEANS DATA=sample MEAN STD;
    VAR score;
RUN;
```
이 예제는 `score` 변수에 대한 평균과 표준 편차를 계산합니다.

### 여러 변수에 대한 통계
```sas
DATA scores;
    INPUT student_id score1 score2;
    DATALINES;
    1 85 90
    2 78 88
    3 92 94
    4 70 76
    ;
RUN;

PROC MEANS DATA=scores MEAN STD;
    VAR score1 score2;
RUN;
```
위 코드는 `score1`과 `score2` 두 변수의 평균과 표준 편차를 계산합니다.

## 설명
### 일반적인 함정 및 유의사항
- **NA 값 처리**: PROC MEANS는 기본적으로 결측값을 무시하므로, 결측값이 많을 경우 결과가 왜곡될 수 있습니다. 필터링이나 데이터 클리닝이 필요할 수 있습니다.
- **집계 수준**: 그룹화된 통계를 원할 경우, `CLASS` 문을 사용하여 그룹별 통계를 계산할 수 있습니다.
- **출력 옵션**: `OUTPUT` 문을 사용하여 통계량을 새로운 데이터셋으로 저장할 수 있습니다.

## 한 줄 요약
PROC MEANS는 SAS에서 데이터셋의 다양한 기술 통계를 손쉽게 계산할 수 있는 강력한 도구입니다.