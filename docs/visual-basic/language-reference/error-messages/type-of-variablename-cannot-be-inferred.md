---
title: Тип <variablename> не может быть выведен, поскольку для границ цикла и переменной шага нет расширяющего преобразования к одному типу
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: e90e881546c12df2c8b19ff03a4d4c7304c4596c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815879"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>Тип "\<имя_переменной >" не могут быть получены, так как границы цикла и переменной шага нет расширяющего преобразования к одному типу
Вы написали `For...Next` цикл, в котором компилятор не может вывести тип данных для управляющей переменной цикла, потому, что выполняются следующие условия:  
  
-   Тип данных управляющей переменной цикла не указан с помощью выражения `As` .  
  
-   Границы цикла и переменная шага содержат по крайней мере два типа данных.  
  
-   Нет стандартных преобразований между типами данных.  
  
 Таким образом компилятор не может вывести тип данных управляющей переменной цикла.  
  
 В следующем примере переменной шага является символом и границы цикла — оба целые числа. Так как стандартные преобразования между символами и целых чисел, не существует, возникает следующая ошибка.  
  
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
  
-   Измените типы границ цикла и переменной шага, чтобы по крайней мере один из них — это тип, остальные расширяющего преобразования к. В предыдущем примере, измените тип `stepVar` для `Integer`.  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     —или—  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   Используйте функции явного преобразования для преобразования границ цикла и переменной шага в соответствующие типы. В приведенном выше примере применяются `Val` функция `stepVar`.  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Расширяющие и сужающие преобразования](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
