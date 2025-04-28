<!--
Meta Description: # SAS 中的 END 命令：用法及示例 ## 簡介 在 SAS 程式語言中，`END` 是一個關鍵字，主要用於控制資料步驟的流程，特別是在 `DO` 循環和 `SELECT` 語句中。它幫助程式員結束特定的控制結構，確保程式的正確執行。 ## 文檔 ### 目的 `END` 命令的主要目的是指示...
Meta Keywords: end, select, sas, 語句中, when
-->

# SAS 中的 END 命令：用法及示例

## 簡介
在 SAS 程式語言中，`END` 是一個關鍵字，主要用於控制資料步驟的流程，特別是在 `DO` 循環和 `SELECT` 語句中。它幫助程式員結束特定的控制結構，確保程式的正確執行。

## 文檔
### 目的
`END` 命令的主要目的是指示程式在特定的控制結構內部結束執行。這對於多重循環或條件語句尤為重要，能夠清晰地標示出程式的邏輯結束點。

### 使用方法
- 在 `DO` 循環中，`END` 用於標示循環的結束。
- 在 `SELECT` 語句中，`END` 也用於結束 `WHEN` 子句的定義。

### 詳細說明
在 SAS 中，`END` 的使用語法如下：

```sas
DO;
    /* 你的程式碼 */
END;
```

在 `SELECT` 語句中，語法如下：

```sas
SELECT;
    WHEN (條件1) /* 行為1 */;
    WHEN (條件2) /* 行為2 */;
    OTHERWISE /* 預設行為 */;
END;
```

### 注意事項
- 確保在每個 `DO` 或 `SELECT` 結構後正確使用 `END`，否則會導致語法錯誤。
- 在複雜的程式中，確保 `END` 與相應的 `DO` 或 `SELECT` 配對，避免邏輯錯誤。

## 示例
### 基本用法示例
```sas
data example;
    do i = 1 to 5;
        output;
    end;
run;

proc sql;
    select name
    from sashelp.class
    where age > 12
    order by age;
quit;
```

在上述示例中，`END` 標示了 `DO` 循環的結束和 `SELECT` 語句的結束。

## 解釋
常見的陷阱包括：
- 忘記在 `DO` 循環或 `SELECT` 語句中添加 `END`，這會導致程式無法執行。
- 在多層嵌套結構中，未能正確對應 `END` 和 `DO` 或 `SELECT`，可能導致意外的執行結果。

## 一句總結
`END` 是 SAS 中用於結束 `DO` 循環和 `SELECT` 語句的重要關鍵字，確保程式邏輯的正確執行。