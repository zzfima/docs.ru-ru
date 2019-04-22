---
title: Практическое руководство. Защита аргумента процедуры от изменения значения (Visual Basic)
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
ms.openlocfilehash: 70378b57c6d3af5a98e0ba9c6e3aebc319561b1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837784"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Практическое руководство. Защита аргумента процедуры от изменения значения (Visual Basic)
Если процедура объявляет параметр как [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic предоставляет код процедуры прямую ссылку на элемент программирования, в аргументе в вызывающем коде. Это позволяет процедуре для изменения значения в аргументе в вызывающем коде. В некоторых случаях вызывающий код может потребоваться защита от таких изменений.  
  
 Всегда можно защитить аргумент от изменений, объявив соответствующий параметр [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) в процедуре. Если вы хотите иметь возможность изменять данный аргумент в некоторых случаях, но не другие, его можно объявить `ByRef` и позволить вызывающему коду определять механизм передачи в каждом вызове. Это достигается путем заключения в круглые скобки, чтобы передать его по значению соответствующего аргумента, или не заключать в круглые скобки, чтобы передавать по ссылке. Дополнительные сведения см. в разделе [Как Принудительная передаваться по значению аргумента](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Пример  
 Следующий пример показывает две процедуры, которые принимают переменную массива и работают на его элементы. `increase` Процедура добавляет единицу к каждому элементу. `replace` Процедура присваивает новый массив в параметре `a()` и добавляет единицу к каждому элементу. Тем не менее переназначение не влияет на базовую переменную массива в вызывающем коде.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Первый `MsgBox` вызове отображается «после увеличения (n): 11, 21, 31, 41". Так как массив `n` является ссылочным типом, `increase` может изменить его элементы, несмотря на то, что механизм передачи `ByVal`.  
  
 Второй `MsgBox` вызове отображается «после замены(n): 11, 21, 31, 41". Так как `n` передается `ByVal`, `replace` нельзя изменить переменную `n` в вызывающем коде путем назначения ей новый массив. Когда `replace` создает новый экземпляр массива `k` и назначает его локальной переменной `a`, он теряет ссылку на `n` передается в вызывающий код. При его переходе членами `a`, только локальный массив `k` снижается. Таким образом `replace` не увеличивает значения массива `n` в вызывающем коде.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 По умолчанию в Visual Basic используется для передачи аргументов по значению. Тем не менее, рекомендуется использовать одну [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром. Это делает код более удобным для чтения.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Различия между изменяемыми и неизменяемыми аргументами](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Практическое руководство. Изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)
- [Практическое руководство. Принудительная передаваться по значению аргумента](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
