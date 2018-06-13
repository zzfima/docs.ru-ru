---
title: Тип &#39; &lt;variablename&gt; &#39; невозможно вывести, поскольку границы цикла и переменной шага нет расширяющего преобразования к одному типу
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: d6fdd9445b5336773d150c643c7bf1ca58a0c87a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597156"
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>Тип &#39; &lt;variablename&gt; &#39; невозможно вывести, поскольку границы цикла и переменной шага нет расширяющего преобразования к одному типу
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
