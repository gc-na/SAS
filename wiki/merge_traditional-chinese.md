<!--
Meta Description: # SAS 中的 MERGE 命令：數據合併的利器 ## 概述 在 SAS 程序中，`MERGE` 命令用於將多個數據集根據一個或多個共通變數進行合併。這個功能對於數據整合、數據清理和數據分析至關重要，能夠有效地將不同來源的數據結合在一起。 ## 文檔 ### 目的 `MERGE` 命令的主要目的是...
Meta Keywords: merge, data, sas, dataset1, dataset2
-->

# SAS 中的 MERGE 命令：數據合併的利器

## 概述
在 SAS 程序中，`MERGE` 命令用於將多個數據集根據一個或多個共通變數進行合併。這個功能對於數據整合、數據清理和數據分析至關重要，能夠有效地將不同來源的數據結合在一起。

## 文檔
### 目的
`MERGE` 命令的主要目的是將多個數據集結合為一個單一數據集，這通常在進行數據分析時需要使用多個來源的數據。

### 使用方法
`MERGE` 命令通常用於 DATA 步驟中，其基本語法如下：

```sas
DATA output_dataset;
    MERGE dataset1 dataset2;
    BY common_variable;
RUN;
```

- `output_dataset`：合併後生成的新數據集。
- `dataset1` 和 `dataset2`：要合併的原始數據集。
- `common_variable`：用來匹配的共通變數，應在所有參與合併的數據集中存在。

### 詳細說明
- 在使用 `MERGE` 時，所有參與合併的數據集必須按指定的共通變數進行排序。
- 如果某個數據集在特定的共通變數上沒有匹配項，則合併後的結果將會在該變數的位置顯示缺失值。
- `MERGE` 命令支持多個數據集的合併，可以通過在命令中列出多個數據集來實現。

## 示例
### 基本用法示例
```sas
/* 數據集1 */
DATA dataset1;
    INPUT ID Name $;
    DATALINES;
1 Alice
2 Bob
3 Charlie
;
RUN;

/* 數據集2 */
DATA dataset2;
    INPUT ID Score;
    DATALINES;
1 85
2 90
4 75
;
RUN;

/* 合併數據集 */
DATA merged_dataset;
    MERGE dataset1 dataset2;
    BY ID;
RUN;

/* 查看合併結果 */
PROC PRINT DATA=merged_dataset;
RUN;
```

在以上示例中，兩個數據集 `dataset1` 和 `dataset2` 透過 `ID` 變數進行合併，最終生成了 `merged_dataset`。

## 解釋
- **常見陷阱**：如果未對所有參與合併的數據集按共通變數進行排序，將會導致合併結果不正確。
- **注意事項**：在多個數據集合併時，需確保共通變數在所有數據集中均存在，否則將出現缺失值。
- **合併方式**：`MERGE` 命令進行的是內部合併，這意味著只有在所有數據集中的共通變數有匹配的記錄才會出現在輸出中。

## 總結
`MERGE` 命令是 SAS 中強大的數據合併工具，能夠有效整合來自不同來源的數據集。