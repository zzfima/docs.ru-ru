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
ms.openlocfilehash: d2e131b770d8498a634d946a5900f9b373ca7e56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651522"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Практическое руководство. Защита аргумента процедуры от изменения значения (Visual Basic)
Если процедура объявляет параметр как [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic предоставляет код процедуры прямую ссылку на элемент программирования в аргументе в вызывающем коде. Это позволяет процедуре для изменения значения, содержащегося в аргументе в вызывающем коде. В некоторых случаях вызывающий код может потребоваться защитить от таких изменений.  
  
 Всегда можно защитить аргумент от изменений, объявив соответствующий параметр [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) в процедуре. Если вы хотите иметь возможность изменять данный аргумент, в некоторых случаях, но не другие, его можно объявить `ByRef` и позволить вызывающему коду определять механизм передачи в каждом вызове. Это делается путем заключения соответствующего аргумента в круглые скобки, чтобы передать его по значению или не заключать в круглые скобки, чтобы передать его по ссылке. Дополнительные сведения см. в разделе [как: Принудительная передача аргумента передается значение](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Пример  
 Следующий пример показывает две процедуры, которые принимают переменную массива и работать над его элементами. `increase` Процедура добавляет единицу к каждому элементу. `replace` Процедура присваивает новый массив параметру `a()` и добавляет единицу к каждому элементу. Однако переопределение не влияет на базовую переменную массива в вызывающем коде.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 Первый `MsgBox` вызове отображается «после увеличения (n): 11, 21, 31, 41». Так как массив `n` является ссылочным типом, `replace` может изменить его элементы, несмотря на то, что механизм передачи `ByVal`.  
  
 Второй `MsgBox` вызове отображается «после замены(n): 11, 21, 31, 41». Поскольку `n` передается `ByVal`, `replace` не может изменить переменную `n` в вызывающем коде, присвоив ей новый массив. Когда `replace` создает новый экземпляр массива `k` и присваивает его локальной переменной `a`, он теряет ссылку на `n` передается в вызывающий код. Когда он изменяет элементы `a`, только локальный массив `k` зависит. Таким образом `replace` не увеличивает значения из массива `n` в вызывающем коде.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 По умолчанию в Visual Basic используется для передачи аргументов по значению. Тем не менее, это хороший стиль программирования способ включения либо [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром. Это делает код более удобным для чтения.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)  
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)  
 [Различия между изменяемыми и неизменяемыми аргументами](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Практическое руководство. Изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Практическое руководство. Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
