---
title: "Тип &lt;имяПеременной&gt; не может быть выведен, поскольку для границ цикла и переменной шага нет расширяющего преобразования к одному типу | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30982"
  - "vbc30982"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30982"
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Тип &lt;имяПеременной&gt; не может быть выведен, поскольку для границ цикла и переменной шага нет расширяющего преобразования к одному типу
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Написан цикл `For...Next`, в котором компилятор не может определить тип данных для переменной цикла, из\-за следующих условий:  
  
-   Тип данных переменной цикла не указан при помощи предложения `As`.  
  
-   Границы цикла и переменная шага содержат, по крайней мере, два типа.  
  
-   Нет стандартных преобразований типов данных.  
  
 Поэтому компилятор не определяет тип данных переменной, управляющей циклом.  
  
 В следующем примере шаг переменной является символом, а обе границы цикла являются целыми числами.  Из\-за отсутствия стандартного преобразования между символами и целыми числами возникает следующая ошибка.  
  
```vb#  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 **Идентификатор ошибки**: BC30982  
  
### Чтобы исправить эту ошибку  
  
-   Измените тип границы цикла либо переменной шага таким образом, чтобы можно было применить расширяющее преобразование к остальным типам.  В предыдущем примере измените тип с `stepVar` на `Integer`.  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     —или—  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   Используйте функции явного преобразования для преобразования границ цикла и переменной шага в соответствующие типы.  В предыдущем примере примените функцию `Val` к `stepVar`.  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## См. также  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>   
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer \- оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)