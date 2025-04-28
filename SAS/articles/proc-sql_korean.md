<!--
Meta Description: # PROC SQL: SAS에서 SQL 프로시저의 활용 ## 개요 PROC SQL은 SAS에서 SQL(Structured Query Language)을 사용하여 데이터베이스에 대한 쿼리를 작성하고, 데이터 조작 및 분석을 수행할 수 있는 강력한 프로시저입니다. 이를 통...
Meta Keywords: proc, sql, 데이터, sas, select
-->

# PROC SQL: SAS에서 SQL 프로시저의 활용

## 개요
PROC SQL은 SAS에서 SQL(Structured Query Language)을 사용하여 데이터베이스에 대한 쿼리를 작성하고, 데이터 조작 및 분석을 수행할 수 있는 강력한 프로시저입니다. 이를 통해 사용자는 데이터를 효율적으로 조회하고, 집계하며, 조합할 수 있습니다.

## 문서화

### 목적
PROC SQL은 SAS 환경 내에서 SQL 쿼리를 사용하여 데이터 세트를 관리하고 처리하는 데 도움을 줍니다. 이 프로시저는 데이터베이스와의 인터페이스 역할을 하며, 복잡한 데이터 조작을 간단하게 수행할 수 있도록 합니다.

### 사용법
PROC SQL의 기본 구문은 다음과 같습니다:

```sas
PROC SQL;
   /* SQL 명령어 */
QUIT;
```

- **SELECT**: 특정 열을 선택하여 데이터를 조회합니다.
- **FROM**: 데이터를 가져올 테이블 또는 데이터 세트를 지정합니다.
- **WHERE**: 조건을 지정하여 필터링된 결과를 반환합니다.
- **ORDER BY**: 결과를 정렬합니다.
- **GROUP BY**: 데이터 집계를 위한 그룹화합니다.

### 세부 사항
PROC SQL은 SAS 데이터 세트, SQL 데이터베이스, ODBC 소스 등 다양한 데이터 소스와 연동이 가능하며, 서브쿼리, 조인, 집계 함수와 같은 고급 SQL 기능도 지원합니다. 또한, SQL을 사용하면 SAS 프로시저와 다른 데이터 조작 방법보다 더 간결하고 직관적인 코드 작성을 가능하게 합니다.

## 예시
1. 기본 SELECT 쿼리:
   ```sas
   PROC SQL;
      SELECT name, age
      FROM sashelp.class;
   QUIT;
   ```

2. 조건을 포함한 쿼리:
   ```sas
   PROC SQL;
      SELECT name, age
      FROM sashelp.class
      WHERE age > 12;
   QUIT;
   ```

3. 정렬된 결과:
   ```sas
   PROC SQL;
      SELECT name, age
      FROM sashelp.class
      ORDER BY age DESC;
   QUIT;
   ```

4. 그룹화 및 집계:
   ```sas
   PROC SQL;
      SELECT sex, COUNT(*) AS count
      FROM sashelp.class
      GROUP BY sex;
   QUIT;
   ```

## 설명
PROC SQL을 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **대소문자 구분**: SQL의 키워드는 대소문자를 구분하지 않지만, 데이터 세트와 열 이름은 대소문자를 구분할 수 있습니다.
- **NULL 값 처리**: SQL에서는 NULL 값을 특별히 처리해야 하며, 이를 무시하거나 잘못된 결과를 초래할 수 있습니다.
- **복잡한 쿼리**: 복잡한 쿼리는 성능 저하를 일으킬 수 있으므로, 최적화를 고려해야 합니다.
- **종속성**: PROC SQL 내에서 생성된 데이터 세트는 다른 프로시저에서 사용할 수 있지만, PROC SQL 세션이 종료되면 데이터 세트가 삭제될 수 있습니다.

## 한 줄 요약
PROC SQL은 SAS에서 SQL을 사용하여 데이터 쿼리 및 조작을 간단하고 효율적으로 수행할 수 있는 프로시저입니다.