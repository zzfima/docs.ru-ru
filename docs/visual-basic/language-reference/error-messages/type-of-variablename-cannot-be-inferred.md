---
title: Тип <variablename> не может быть выведен, поскольку для границ цикла и переменной шага нет расширяющего преобразования к одному типу
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: c3086f79fb71693810bc8f14e8c0f493aa1e6515
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512710"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>Тип "\<variablename >" не может быть определен, так как границы цикла и переменная шага не расширяются до того же типа.

Вы написали `For...Next` цикл, в котором компилятор не может определить тип данных для управляющей переменной цикла, так как выполняются следующие условия.

- Тип данных управляющей переменной цикла не указан с помощью выражения `As` .

- Границы цикла и переменная шага содержат по крайней мере два типа данных.

- Между типами данных не существует стандартных преобразований.

 Таким образом, компилятор не может определить тип данных управляющей переменной цикла.

 В следующем примере переменная шага является символом, а границы цикла — обоими целыми числами. Так как нет стандартного преобразования между символами и целыми числами, возникает эта ошибка.

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

- При необходимости измените типы границ цикла и переменной шага, чтобы по крайней мере один из них был типом, расширяющимся в. В предыдущем примере измените тип `stepVar` на. `Integer`

  ```vb
  Dim stepVar = 1
  ```

  -или-

  ```vb
  Dim stepVar As Integer = 1
  ```

- Используйте явные функции преобразования для преобразования границ цикла и переменной Step в соответствующие типы. В предыдущем примере примените `Val` функцию к. `stepVar`

  ```vb
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
