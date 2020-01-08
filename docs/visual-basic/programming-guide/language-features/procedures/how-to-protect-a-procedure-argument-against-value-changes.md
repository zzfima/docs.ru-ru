---
title: Практическое руководство. Защита аргумента процедуры от изменения значения
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: 75c718c83f36e2f0b2c4cfb5504c2d740eaa3520
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347905"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Практическое руководство. Защита аргумента процедуры от изменения значения (Visual Basic)
Если процедура объявляет параметр как [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic предоставляет коду процедуры прямую ссылку на программный элемент, лежащий в основе аргумента в вызывающем коде. Это позволяет процедуре изменять значение, которое является базовым для аргумента в вызывающем коде. В некоторых случаях вызывающему коду может потребоваться защититься от такого изменения.  
  
 Вы всегда можете защитить аргумент от изменения, объявив соответствующий параметр [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) в процедуре. Если вы хотите иметь возможность изменять заданный аргумент в некоторых случаях, но не в других, можно объявить его `ByRef` и позволить вызывающему коду определить механизм передачи в каждом вызове. Это достигается путем заключения соответствующего аргумента в круглые скобки для передачи его по значению или его заключения в круглые скобки для передачи его по ссылке. Дополнительные сведения см. [в разделе инструкции. Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показаны две процедуры, которые принимают переменную массива и работают с ее элементами. `increase` процедура просто добавляет по одной к каждому элементу. `replace` процедура присваивает новый массив параметру `a()` а затем добавляет его к каждому элементу. Однако переназначение не влияет на базовую переменную массива в вызывающем коде.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Первый вызов `MsgBox` выводит "после увеличения (n): 11, 21, 31, 41". Поскольку массив `n` является ссылочным типом, `increase` может изменять его члены, даже если механизм передачи `ByVal`.  
  
 Во втором вызове `MsgBox` отображается "After Replace (n): 11, 21, 31, 41". Поскольку `n` передается `ByVal`, `replace` не может изменить переменную `n` в вызывающем коде, назначив ей новый массив. Когда `replace` создает новый экземпляр массива `k` и присваивает его локальной переменной `a`, он теряет ссылку на `n`, переданный вызывающим кодом. При изменении членов `a`затрагивается только локальный `k` массива. Таким образом, `replace` не увеличивает значения массива `n` в вызывающем коде.  
  
## <a name="compile-the-code"></a>Компиляция кода  
 По умолчанию в Visual Basic передаются аргументы по значению. Однако рекомендуется включать ключевое слово [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) с каждым объявленным параметром. Это упрощает чтение кода.  
  
## <a name="see-also"></a>См. также:

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Различия между изменяемыми и неизменяемыми аргументами](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Практическое руководство. Изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)
- [Практическое руководство. Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
