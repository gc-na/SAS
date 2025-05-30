<!--
Meta Description: # SAS中的RUN命令：執行程式碼的關鍵指令 ## 簡介 在SAS中，`RUN`命令是一個關鍵指令，用於告訴SAS執行當前的程式碼塊。無論是數據步驟還是程序步驟，`RUN`命令都是促使SAS處理指令並生成結果的必要元素。 ## 文檔 `RUN`命令的主要目的是執行前面所寫的程式碼。當SAS讀取到`...
Meta Keywords: run, data, example, proc, step
-->

# SAS中的RUN命令：執行程式碼的關鍵指令

## 簡介
在SAS中，`RUN`命令是一個關鍵指令，用於告訴SAS執行當前的程式碼塊。無論是數據步驟還是程序步驟，`RUN`命令都是促使SAS處理指令並生成結果的必要元素。

## 文檔
`RUN`命令的主要目的是執行前面所寫的程式碼。當SAS讀取到`RUN`命令時，會開始執行前面的數據步驟或程序步驟，並完成所有指定的操作。這是SAS程式執行過程中的一個重要環節。

### 用法
- `RUN;`命令通常用於數據步驟（DATA step）或程序步驟（PROC step）之後。
- 在SAS程式中，每當需要執行一段程式碼時，必須在該段程式碼的最後添加`RUN;`指令。
- `RUN`命令不需要任何參數。

### 詳細說明
- `RUN`命令必須獨立於其他命令，並且每個`RUN`命令應單獨處理。如果在一個數據步驟中有多個步驟，則每個步驟結束時都必須加上`RUN`命令。
- 在某些情況下，例如在使用`ODS`（輸出交付系統）時，`RUN`命令可能會影響輸出格式，因此需謹慎使用。

## 示例
以下是使用`RUN`命令的基本範例：

### 範例1：數據步驟
```sas
DATA example;
    SET sashelp.class;
    IF age > 13 THEN status = 'Teenager';
RUN;
```
在這個範例中，`RUN`命令告訴SAS執行數據步驟，並將結果存儲在名為`example`的數據集中。

### 範例2：程序步驟
```sas
PROC PRINT DATA=example;
RUN;
```
這裡，`RUN`命令用於執行`PRINT`過程，以顯示`example`數據集的內容。

## 解釋
常見的錯誤或注意事項如下：
- 忘記添加`RUN;`命令會導致SAS不執行前面的程式碼，並顯示錯誤消息。
- 在使用多個`PROC`或`DATA`步驟時，必須為每一個步驟添加`RUN;`命令，以確保程式能夠正確執行。
- 在某些情況下，程序的執行可能需要時間，特別是當處理大型數據集時，因此在執行時需耐心等待。

## 總結
`RUN`命令是SAS中不可或缺的指令，用於啟動程式碼的執行並生成結果。