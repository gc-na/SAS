<!--
Meta Description: # PROC FREQ في لغة SAS: تحليل التكرارات بكفاءة ## الملخص يعد PROC FREQ أمرًا قويًا في لغة SAS لتحليل التكرارات، حيث يمكنه حساب وتقديم تكرارات القيم في...
Meta Keywords: freq, proc, البيانات, sas, تحليل
-->

# PROC FREQ في لغة SAS: تحليل التكرارات بكفاءة

## الملخص
يعد PROC FREQ أمرًا قويًا في لغة SAS لتحليل التكرارات، حيث يمكنه حساب وتقديم تكرارات القيم في مجموعة بيانات، مما يساعد في فهم البيانات بشكل أفضل.

## الوثائق
يهدف PROC FREQ إلى حساب التكرارات والنسب المئوية للقيم في متغيرات معينة. هذا الأمر مفيد بشكل خاص في تحليل البيانات الوصفية، مثل البيانات الفئوية.

### الاستخدام
يمكن استخدام PROC FREQ على النحو التالي:
```sas
PROC FREQ DATA=اسم_مجموعة_البيانات;
    TABLES متغيرات;
RUN;
```
- **DATA**: يشير إلى مجموعة البيانات التي سيتم تحليلها.
- **TABLES**: تحدد المتغيرات التي ترغب في حساب تكراراتها.

### التفاصيل
- يمكن استخدام PROC FREQ مع العديد من الخيارات مثل:
  - `ORDER=`: لتحديد ترتيب القيم.
  - `NOCUM`: لإلغاء عرض التكرارات التراكمية.
  - `OUT=`: لإنشاء مجموعة بيانات جديدة تحتوي على النتائج.

## الأمثلة
### مثال 1: تحليل تكرار بسيط
```sas
DATA مثال;
    INPUT جنس $;
    DATALINES;
    ذكر
    أنثى
    ذكر
    ذكر
    أنثى
    ;
RUN;

PROC FREQ DATA=مثال;
    TABLES جنس;
RUN;
```

### مثال 2: تحليل تكرار مع خيارات إضافية
```sas
PROC FREQ DATA=مثال ORDER=FREQ NOCUM;
    TABLES جنس / OUT=نتائج;
RUN;
```

## الشرح
عند استخدام PROC FREQ، هناك بعض النقاط الهامة التي يجب الانتباه لها:
- **التكرارات الصفرية**: قد لا يتم عرض القيم التي لم تظهر في مجموعة البيانات.
- **حجم البيانات**: يمكن أن يؤثر حجم مجموعة البيانات على أداء الأمر، خاصةً عند تحليل متغيرات متعددة.

## ملخص من سطر واحد
يعتبر PROC FREQ أداة فعّالة في SAS لتحليل تكرارات القيم في المتغيرات، مما يسهم في فهم البيانات بشكل أفضل.