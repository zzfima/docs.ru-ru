---
title: Практическое руководство. Изменение значения аргумента процедуры (Visual Basic)
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
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: a56bdf888163c9559b87e857abb33522c547ed45
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316626"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Практическое руководство. Изменение значения аргумента процедуры (Visual Basic)
При вызове процедуры, каждый аргумент соответствует одному из параметров, определенных в процедуре. В некоторых случаях код процедуры можно изменить значение базового аргумента в вызывающем коде. В других случаях процедуру можно изменить только свою локальную копию аргумента.  
  
 При вызове процедуры, Visual Basic производит локальную копию каждый аргумент, передаваемый [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Для каждого передаваемого аргумента [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic предоставляет код процедуры прямую ссылку на элемент программирования, в аргументе в вызывающем коде.  
  
 Если элемент в вызывающем коде является изменяемым и аргумент, передаваемый `ByRef`, код процедуры можно использовать прямую ссылку, чтобы изменить значение этого элемента в вызывающем коде.  
  
## <a name="changing-the-underlying-value"></a>Изменение базового значения  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Чтобы изменить базовое значение аргумента в вызывающем коде процедуры  
  
1. В объявлении процедуры, указывать [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для параметра, соответствующего аргументу.  
  
2. В вызывающем коде передайте изменяемый элемент программирования в качестве аргумента.  
  
3. В вызывающем коде не заключайте аргумент в списке аргументов в скобках.  
  
4. В коде процедуры используйте имя параметра для присвоения значения базового элемента в вызывающем коде.  
  
 См. в примере ниже для демонстрации.  
  
## <a name="changing-local-copies"></a>Изменение локальных копий  
 Если элемент в вызывающем коде является неизменяемым или если аргумент, передаваемый `ByVal`, процедура не может изменить его значение в вызывающий код. Тем не менее процедура может изменять свою локальную копию такого аргумента.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>Чтобы изменить копию аргумента процедуры в коде процедуры  
  
1. В объявлении процедуры, указывать [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) для параметра, соответствующего аргументу.  
  
     -или-  
  
     В вызывающем коде заключите аргумент в списке аргументов в скобках. Это заставляет Visual Basic для передачи аргумента по значению, даже если соответствующий параметр указывает `ByRef`.  
  
2. В коде процедуры используйте имя параметра для присвоения значения аргумента в локальной копии. Базовое значение в вызывающий код не изменяется.  
  
## <a name="example"></a>Пример  
 Следующий пример показывает две процедуры, которые принимают переменную массива и работают на его элементы. `increase` Процедура добавляет единицу к каждому элементу. `replace` Процедура присваивает новый массив в параметре `a()` и добавляет единицу к каждому элементу.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Первый `MsgBox` вызове отображается «после увеличения (n): 11, 21, 31, 41". Так как массив `n` является ссылочным типом, `replace` может изменить его элементы, несмотря на то, что механизм передачи `ByVal`.  
  
 Второй `MsgBox` вызове отображается «после замены(n): 101, 201, 301". Так как `n` передается `ByRef`, `replace` можно изменить переменную `n` в вызывающий код и присвоить ей новый массив, к нему. Так как `n` является ссылочным типом, `replace` также можно менять ее членов.  
  
 Можно запретить процедуре изменять переменную в вызывающем коде. См. практическое руководство по [ Защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Если переменная передается по ссылке, необходимо использовать `ByRef` ключевое слово, чтобы указать этот механизм.  
  
 По умолчанию в Visual Basic используется для передачи аргументов по значению. Тем не менее, рекомендуется использовать одну [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром. Это делает код более удобным для чтения.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Всегда найдется потенциальную угрозу в разрешении процедуре измените значение базового аргумента в вызывающем коде. Убедитесь, что предполагается, что это значение, чтобы изменить и будьте готовы, проверяемый на допустимость перед его использованием.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Различия между изменяемыми и неизменяемыми аргументами](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Практическое руководство. Защита аргумента процедуры от изменений значения](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Практическое руководство. Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
