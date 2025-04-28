<!--
Meta Description: # SAS에서 FILENAME 구문: 파일 참조 및 데이터 처리의 기초 ## 개요 SAS의 FILENAME 구문은 외부 파일이나 데이터 소스를 참조하는 데 사용됩니다. 이 명령어를 통해 SAS 프로그램 내에서 파일을 효율적으로 관리하고, 데이터 입력 및 출력을 원활하게...
Meta Keywords: filename, 데이터, 있습니다, sas, data
-->

# SAS에서 FILENAME 구문: 파일 참조 및 데이터 처리의 기초

## 개요
SAS의 FILENAME 구문은 외부 파일이나 데이터 소스를 참조하는 데 사용됩니다. 이 명령어를 통해 SAS 프로그램 내에서 파일을 효율적으로 관리하고, 데이터 입력 및 출력을 원활하게 수행할 수 있습니다.

## 문서화

### 목적
FILENAME 구문은 SAS에서 외부 파일(예: 텍스트 파일, 엑셀 파일 등)을 참조하거나, SAS 데이터 세트를 저장할 위치를 지정하는 데 사용됩니다. 이를 통해 데이터 관리와 처리의 효율성을 높일 수 있습니다.

### 사용법
FILENAME 구문의 기본 형식은 다음과 같습니다:

```sas
FILENAME fileref '파일경로';
```

- **fileref**: 파일 참조 이름. 사용자 정의 이름으로, 다른 SAS 구문에서 이 이름을 사용하여 파일에 접근할 수 있습니다.
- **파일경로**: 참조할 외부 파일의 경로. 시스템에 따라 절대 경로 또는 상대 경로를 사용할 수 있습니다.

### 세부사항
- FILENAME 구문은 데이터 입력(Input) 및 출력(Output) 작업에서 매우 중요합니다.
- 다양한 파일 형식을 지원하며, 각 파일 형식에 맞는 옵션을 추가로 지정할 수 있습니다.
- FILENAME 구문을 사용하여 여러 파일을 동시에 참조할 수 있으며, 필요에 따라 파일 참조를 해제할 수도 있습니다.

## 예제

### 기본 사용 예제
```sas
/* 텍스트 파일 참조 */
FILENAME myfile 'C:\data\example.txt';

/* CSV 파일에서 데이터 읽기 */
DATA mydata;
    INFILE myfile;
    INPUT var1 var2 var3;
RUN;

/* 텍스트 파일로 데이터 출력 */
DATA _NULL_;
    FILE myfile;
    PUT 'Hello, SAS!';
RUN;
```

### 여러 파일 참조
```sas
/* 여러 파일 참조 */
FILENAME myfile1 'C:\data\example1.txt';
FILENAME myfile2 'C:\data\example2.txt';

/* 첫 번째 파일에서 데이터 읽기 */
DATA data1;
    INFILE myfile1;
    INPUT var1 var2;
RUN;

/* 두 번째 파일에 데이터 출력 */
DATA _NULL_;
    FILE myfile2;
    PUT 'This is another example.';
RUN;
```

## 설명
- **파일 경로 오류**: 지정한 파일 경로가 잘못되면 파일을 찾을 수 없으므로 정확한 경로를 확인해야 합니다.
- **파일 형식**: 읽고자 하는 파일의 형식에 맞는 INFILE 옵션을 사용하지 않으면 데이터 입력에 실패할 수 있습니다.
- **파일 참조 해제**: FILENAME 구문으로 생성한 파일 참조는 프로그램 종료 시 자동으로 해제되지만, 필요에 따라 `FILENAME fileref CLEAR;` 구문을 사용하여 수동으로 해제할 수 있습니다.

## 한 줄 요약
SAS의 FILENAME 구문은 외부 파일을 참조하고, 데이터 입력 및 출력을 관리하는 데 필수적인 명령어입니다.