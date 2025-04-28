<!--
Meta Description: # ELSE 在 SAS 中的使用 ## 摘要 在 SAS 程式中，`ELSE` 是一個控制結構，用於在 `IF` 條件判斷不成立時執行替代代碼區塊。這使得程式能夠在多種情況下進行有效的邏輯控制，提升程式的靈活性和可讀性。 ## 文檔 `ELSE` 是 SAS 程式語言中的一個關鍵字，經常與 `IF...
Meta Keywords: else, sas, score, then, data
-->

# ELSE 在 SAS 中的使用

## 摘要
在 SAS 程式中，`ELSE` 是一個控制結構，用於在 `IF` 條件判斷不成立時執行替代代碼區塊。這使得程式能夠在多種情況下進行有效的邏輯控制，提升程式的靈活性和可讀性。

## 文檔
`ELSE` 是 SAS 程式語言中的一個關鍵字，經常與 `IF` 語句搭配使用，形成條件語句的邏輯結構。其主要目的是在特定條件不滿足時執行另一段程式碼，從而能夠根據不同的情境做出相應的處理。

### 用法
`ELSE` 的基本語法如下：

```sas
IF condition THEN do;
    /* 當條件成立時執行的程式碼 */
END;
ELSE do;
    /* 當條件不成立時執行的程式碼 */
END;
```

在 SAS 中，您可以使用 `ELSE IF` 來檢查多個條件，這樣程式能夠更精細地控制邏輯流程。

### 詳細說明
- `ELSE` 讓程式在 `IF` 條件不成立時提供備選方案。
- 可以與 `ELSE IF` 結合使用，從而可以檢查多個條件。
- 在數據步驟中，`ELSE` 也可以用於判斷和處理數據行，以便根據不同的數據值進行相應的操作。

## 範例
以下是使用 `ELSE` 的基本範例：

### 單一條件範例
```sas
data example;
    input score;
    if score >= 60 then pass = 'Yes';
    else pass = 'No';
    datalines;
    75
    45
    80
    ;
run;

proc print data=example;
run;
```

在這個範例中，若 `score` 大於等於 60，則 `pass` 變數為 'Yes'，否則為 'No'。

### 多條件範例
```sas
data example;
    input score;
    if score >= 90 then grade = 'A';
    else if score >= 75 then grade = 'B';
    else grade = 'C';
    datalines;
    95
    80
    60
    ;
run;

proc print data=example;
run;
```

在這個範例中，根據不同的 `score` 成績給出相應的等級。

## 解釋
在使用 `ELSE` 時，常見的陷阱包括：
- 忘記在 `IF` 語句中添加 `THEN`，會導致語法錯誤。
- 在使用 `ELSE IF` 時，條件的檢查順序很重要，錯誤的順序可能會導致意外的結果。
- 不同於某些編程語言，`ELSE` 在 SAS 中必須與 `IF` 配合使用，無法單獨存在。

## 一句總結
`ELSE` 是 SAS 中一個重要的控制結構，用於在 `IF` 條件不成立時執行替代程式碼，從而提升程式的邏輯靈活性。