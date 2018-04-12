---
title: Тип &#39; &lt;variablename&gt;&#39; невозможно вывести, поскольку границы цикла и переменной шага нет расширяющего преобразования к одному типу
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 022e29e38a93d2880bbfa250e65a8b95b39ff140
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>Тип &#39; &lt;variablename&gt;&#39; невозможно вывести, поскольку границы цикла и переменной шага нет расширяющего преобразования к одному типу
Вы написали `For...Next` цикл, в котором компилятор не может вывести тип данных для управляющей переменной цикла, из-за следующих условий:  
  
-   Тип данных управляющей переменной цикла не указан с помощью выражения `As` .  
  
-   Границы цикла и переменная шага содержат по крайней мере два типа данных.  
  
-   Нет стандартных преобразований между типами данных.  
  
 Таким образом компилятор не может определить тип данных переменной цикла.  
  
 В следующем примере шаг переменной является символом и границы цикла являются целыми. Поскольку стандартного преобразования между символами и целыми числами, возникает следующая ошибка.  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 **Идентификатор ошибки:** BC30982  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените типы границ цикла и переменной шага, чтобы по крайней мере один из них — это тип, остальные расширяющего преобразования. В предыдущем примере, измените тип `stepVar` для `Integer`.  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     —или—  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   Используйте функции явного преобразования для преобразования границ цикла и переменной шага в соответствующие типы. В предыдущем примере применить `Val` функция `stepVar`.  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
