---
title: "Практическое руководство: защита аргумента процедуры от изменения значения (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedures, arguments
- procedures, parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6e18f7ceefeec9c1f422d0eae4e727700ebd8b6e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Практическое руководство. Защита аргумента процедуры от изменения значения (Visual Basic)
Если процедура объявляет параметр как [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет код процедуры прямую ссылку на программный элемент, лежащий в основе аргумента в вызывающем коде. Это позволяет процедуре изменять значение базового аргумента в вызывающем коде. В некоторых случаях вызывающему коду может потребоваться защита от таких изменений.  
  
 Всегда можно защитить аргумент от изменений, объявив соответствующий параметр [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) в процедуре. Если вы хотите иметь возможность изменять данный аргумент, в некоторых случаях, но не другие, его можно объявить `ByRef` и позволить вызывающему коду определять механизм передачи в каждом вызове. Это делается путем заключения соответствующего аргумента в круглые скобки, чтобы передать его по значению или не заключать в круглые скобки, чтобы передать его по ссылке. Дополнительные сведения см. в разделе [как: Принудительная передача аргумента передается значение](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Пример  
 Следующий пример показывает две процедуры, которые принимают переменную массива и производят на его элементы. `increase` Процедура просто добавляет единицу к каждому элементу. `replace` Процедура присваивает новый массив параметру `a()` и затем добавляет единицу к каждому элементу. Однако переназначение не влияет на базовую переменную массива в вызывающем коде.  
  
 [!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#38;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 Первый `MsgBox` вызове отображается «после увеличения (n): 11, 21, 31, 41». Так как массив `n` является ссылочным типом, `replace` может изменить его элементы, несмотря на то, что механизм передачи `ByVal`.  
  
 Второй `MsgBox` вызове отображается «после замены(n): 11, 21, 31, 41». Поскольку `n` передается `ByVal`, `replace` не может изменить переменную `n` в вызывающем коде, присвоив ей новый массив. Когда `replace` создает новый экземпляр массива `k` и назначает его локальной переменной `a`, он теряет ссылку на `n` передается в вызывающий код. Когда он изменяет элементы `a`, только локальный массив `k` изменяется. Таким образом `replace` не увеличивает значения из массива `n` в вызывающем коде.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 По умолчанию в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] аргументы передаются по значению. Тем не менее, хорошим стилем программирования считается включают в себя [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром. Это облегчает чтение кода.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)   
 [Различия между изменяемые и неизменяемые аргументы](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Практическое руководство: изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Практическое руководство: Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
