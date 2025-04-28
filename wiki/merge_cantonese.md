<!--
Meta Description: # SAS 中的 MERGE 命令：數據合併的高效工具 ## 摘要 在 SAS 編程中，`MERGE` 命令用於將兩個或多個數據集根據共同變數進行合併，從而形成一個新的數據集。這種合併方式在數據分析和處理過程中極其重要。 ## 文檔 ### 目的 `MERGE` 命令的主要目的是將多個數據集根據一個...
Meta Keywords: merge, data, run, sas, data1
-->

# SAS 中的 MERGE 命令：數據合併的高效工具

## 摘要
在 SAS 編程中，`MERGE` 命令用於將兩個或多個數據集根據共同變數進行合併，從而形成一個新的數據集。這種合併方式在數據分析和處理過程中極其重要。

## 文檔
### 目的
`MERGE` 命令的主要目的是將多個數據集根據一個或多個共同的鍵（變數）進行整合。這對於需要從不同數據來源整合信息的分析師來說是不可或缺的。

### 用法
`MERGE` 的基本語法如下：
```sas
DATA new_data;
    MERGE dataset1 dataset2;
    BY key_variable;
RUN;
```
在這裡，`new_data` 是合併後產生的新數據集，`dataset1` 和 `dataset2` 是需要合併的原始數據集，而 `key_variable` 則是用於合併的共同變數。

### 詳細說明
- **共用變數**：在進行合併之前，確保所有數據集中的共同變數名稱相同，且數據類型一致。
- **排序要求**：在使用 `MERGE` 之前，必須先對所有參與合併的數據集進行排序。可以使用 `PROC SORT` 來實現。
- **合併類型**：`MERGE` 支持多種合併類型，如內合併（只保留共同鍵的觀察值）、外合併（保留所有觀察值，缺失值用缺失填充）等。

## 範例
### 基本用法
假設有兩個數據集 `data1` 和 `data2`，我們希望根據變數 `id` 進行合併：
```sas
DATA data1;
    INPUT id name $;
    DATALINES;
1 Alice
2 Bob
3 Charlie
;
RUN;

DATA data2;
    INPUT id age;
    DATALINES;
1 25
2 30
4 22
;
RUN;

PROC SORT DATA=data1; BY id; RUN;
PROC SORT DATA=data2; BY id; RUN;

DATA merged_data;
    MERGE data1 data2;
    BY id;
RUN;
```
這段程式碼將生成一個新的數據集 `merged_data`，其中包含 `id`、`name` 和 `age` 三個變數。

## 解釋
### 常見陷阱
- **未排序的數據集**：如果未對數據集進行排序，會導致合併結果不正確。
- **缺失值處理**：使用 `MERGE` 時，對於沒有匹配的觀察值，新的數據集會填充缺失值，這可能會影響後續分析。
- **多重匹配**：如果在合併的過程中有多個匹配，將會產生重複的行，這在分析時需要特別注意。

## 一句總結
`MERGE` 命令是 SAS 中一個強大的工具，可以根據共同變數有效地合併多個數據集。