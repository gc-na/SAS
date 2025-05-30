<!--
Meta Description: # PROC SORT في SAS: ترتيب البيانات بكفاءة ## ملخص تُستخدم PROC SORT في لغة برمجة SAS لترتيب البيانات في مجموعات البيانات (Datasets) بطريقة فعالة، حيث ...
Meta Keywords: البيانات, proc, sort, مجموعة, sas
-->

# PROC SORT في SAS: ترتيب البيانات بكفاءة

## ملخص
تُستخدم PROC SORT في لغة برمجة SAS لترتيب البيانات في مجموعات البيانات (Datasets) بطريقة فعالة، حيث يُعتبر الترتيب خطوة أساسية في معالجة وتحليل البيانات.

## الوثائق
### الغرض
PROC SORT هي إجراء (Procedure) في SAS يُستخدم لترتيب البيانات في مجموعة بيانات معينة بناءً على واحد أو أكثر من المتغيرات. يمكن أن يكون الترتيب تصاعديًا أو تنازليًا.

### الاستخدام
لإجراء عملية الفرز باستخدام PROC SORT، يجب تحديد مجموعة البيانات المستهدفة والمتغيرات التي سيتم الفرز بناءً عليها. تتضمن الصيغة الأساسية:

```sas
PROC SORT DATA=اسم_المجموعة;
    BY [تصاعدي|تنازلي] متغيرات;
RUN;
```

- **DATA**: يحدد مجموعة البيانات المراد ترتيبها.
- **BY**: يُستخدم لتحديد المتغيرات التي سيتم الفرز بناءً عليها. 
- **تصاعدي|تنازلي**: يمكن تحديد نوع الترتيب (التصاعدي هو الافتراضي).

### التفاصيل
- يمكن فرز البيانات بناءً على متغير واحد أو عدة متغيرات.
- عند فرز البيانات، يمكن استخدام خيارات إضافية مثل `OUT=` لتحديد مجموعة بيانات جديدة تحتوي على البيانات المرتبة.
- إذا كانت المتغيرات تحتوي على قيم مفقودة، فإن القيم المفقودة ستظهر في نهاية مجموعة البيانات المرتبة.

## أمثلة
### مثال 1: فرز بسيط
```sas
DATA employees;
    INPUT Name $ Salary;
    DATALINES;
    John 50000
    Alice 60000
    Bob 45000
    ;
RUN;

PROC SORT DATA=employees;
    BY Salary;
RUN;
```
هذا المثال يقوم بفرز مجموعة بيانات `employees` بناءً على راتب الموظفين.

### مثال 2: فرز متعدد
```sas
DATA students;
    INPUT Name $ Age Grade;
    DATALINES;
    Ahmed 20 85
    Sara 22 90
    Ali 20 88
    ;
RUN;

PROC SORT DATA=students;
    BY Age Grade;
RUN;
```
في هذا المثال، يتم فرز مجموعة بيانات `students` أولاً حسب العمر، ثم حسب الدرجة.

## الشرح
### الأخطاء الشائعة
- **نسيان خيار `BY`**: إذا لم يتم تحديد المتغيرات في عبارة `BY`، فلن يتم فرز البيانات.
- **فرز البيانات المفقودة**: قد تؤدي القيم المفقودة إلى نتائج غير متوقعة إذا لم تؤخذ بعين الاعتبار.
- **عدم استخدام `OUT=`**: إذا كنت بحاجة إلى الاحتفاظ بالإصدار الأصلي من البيانات، تأكد من استخدام خيار `OUT=` لإنشاء مجموعة بيانات جديدة.

## ملخص من سطر واحد
PROC SORT في SAS هو إجراء فعال لترتيب البيانات في مجموعات البيانات بناءً على متغيرات محددة.