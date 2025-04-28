<!--
Meta Description: # RUN 命令在 SAS 中的應用 ## 概述 在 SAS（Statistical Analysis System）中，`RUN` 命令是一個基本而重要的指令，用於執行數據步驟或過程步驟。它確保之前的程式碼被執行並完成，從而生成所需的結果。 ## 文件說明 `RUN` 命令的主要目的是告訴 SAS...
Meta Keywords: run, sas, proc, sashelp, class
-->

# RUN 命令在 SAS 中的應用

## 概述
在 SAS（Statistical Analysis System）中，`RUN` 命令是一個基本而重要的指令，用於執行數據步驟或過程步驟。它確保之前的程式碼被執行並完成，從而生成所需的結果。

## 文件說明
`RUN` 命令的主要目的是告訴 SAS 執行先前定義的資料步驟或過程步驟。它通常位於程式碼的結尾，確保所有指令在此之前均已被正確解析並執行。當使用 SAS 編輯器時，`RUN` 命令是必不可少的，因為它標誌著指令的結束並觸發執行。

### 用法
`RUN` 命令的基本格式如下：
```sas
<程式碼>
RUN;
```
例如，您可以在數據步驟或過程步驟之後插入 `RUN` 命令，以執行這些步驟。

### 詳細解釋
- **數據步驟**：在進行數據處理和資料集創建時，`RUN` 命令會告訴 SAS 完成所有操作並生成結果。
- **過程步驟**：在使用 SAS 的各種分析過程時，如 `PROC PRINT` 或 `PROC MEANS`，`RUN` 命令同樣用來執行這些過程。

## 範例
以下是一些 `RUN` 命令的基本使用範例：

### 範例 1：數據步驟
```sas
DATA example;
    SET sashelp.class;
    IF age > 12 THEN status = 'Teen';
    ELSE status = 'Child';
RUN;
```
這段程式碼創建了一個新的資料集 `example`，並在執行後生成結果。

### 範例 2：過程步驟
```sas
PROC MEANS DATA=sashelp.class;
    VAR height weight;
RUN;
```
這段程式碼計算並顯示 `sashelp.class` 資料集中 `height` 和 `weight` 的統計信息。

## 解釋
在使用 `RUN` 命令時，有幾個常見的注意事項：
- **命令必須在每個數據步驟或過程步驟的結尾**：如果缺少 `RUN`，SAS 將無法正確執行程式碼，並可能導致錯誤。
- **避免冗餘**：在不必要的地方重複使用 `RUN` 命令會使程式碼變得雜亂，但在每個主要步驟結尾使用它是必要的。

## 一句話總結
`RUN` 命令在 SAS 中用於執行數據和過程步驟，確保程式碼的正確執行及生成所需的結果。