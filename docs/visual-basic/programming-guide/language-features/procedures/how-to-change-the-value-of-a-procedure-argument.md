---
title: Практическое руководство. Изменение значения аргумента процедуры
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
ms.openlocfilehash: deac87ca4690990a4d00f63d0ea9b843c3f9a9c4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344480"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Практическое руководство. Изменение значения аргумента процедуры (Visual Basic)
При вызове процедуры каждый указываемый аргумент соответствует одному из параметров, определенных в процедуре. В некоторых случаях код процедуры может изменить значение, которое является базовым для аргумента в вызывающем коде. В других случаях процедура может изменить только локальную копию аргумента.  
  
 При вызове процедуры Visual Basic создает локальную копию каждого аргумента, который передается по [значению ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Для каждого аргумента, переданного по [ссылке ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic предоставляет коду процедуры прямую ссылку на программный элемент, лежащий в основе аргумента в вызывающем коде.  
  
 Если базовый элемент в вызывающем коде является изменяемым, а аргумент передается `ByRef`, то код процедуры может использовать прямую ссылку для изменения значения элемента в вызывающем коде.  
  
## <a name="changing-the-underlying-value"></a>Изменение базового значения  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Изменение базового значения аргумента процедуры в вызывающем коде  
  
1. В объявлении процедуры укажите [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для параметра, соответствующего аргументу.  
  
2. В вызывающем коде передайте изменяемый программный элемент в качестве аргумента.  
  
3. В вызывающем коде не заключайте аргумент в круглые скобки в списке аргументов.  
  
4. В коде процедуры используйте имя параметра, чтобы присвоить значение базовому элементу в вызывающем коде.  
  
 Для демонстрации см. пример ниже.  
  
## <a name="changing-local-copies"></a>Изменение локальных копий  
 Если базовый элемент в вызывающем коде является неизменяемым, или если аргумент передается `ByVal`, процедура не может изменить его значение в вызывающем коде. Однако процедура может изменить локальную копию такого аргумента.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>Изменение копии аргумента процедуры в коде процедуры  
  
1. В объявлении процедуры укажите [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) для параметра, соответствующего аргументу.  
  
     \- или -  
  
     В вызывающем коде заключите аргумент в круглые скобки в список аргументов. Это заставляет Visual Basic передавать аргумент по значению, даже если соответствующий параметр указывает `ByRef`.  
  
2. В коде процедуры используйте имя параметра, чтобы присвоить значение локальной копии аргумента. Базовое значение в вызывающем коде не изменяется.  
  
## <a name="example"></a>Пример  
 В следующем примере показаны две процедуры, которые принимают переменную массива и работают с ее элементами. `increase` процедура просто добавляет по одной к каждому элементу. `replace` процедура присваивает новый массив параметру `a()` а затем добавляет его к каждому элементу.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Первый вызов `MsgBox` выводит "после увеличения (n): 11, 21, 31, 41". Поскольку массив `n` является ссылочным типом, `replace` может изменять его члены, даже если механизм передачи `ByVal`.  
  
 Во втором вызове `MsgBox` отображается "After Replace (n): 101, 201, 301". Поскольку `n` передается `ByRef`, `replace` может изменить переменную `n` в вызывающем коде и присвоить ей новый массив. Поскольку `n` является ссылочным типом, `replace` также может изменять его члены.  
  
 Можно запретить процедуре изменять саму переменную в вызывающем коде. См. раздел [как защитить аргумент процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compile-the-code"></a>Компиляция кода  
 При передаче переменной по ссылке необходимо использовать ключевое слово `ByRef` для указания этого механизма.  
  
 По умолчанию в Visual Basic передаются аргументы по значению. Однако рекомендуется включать ключевое слово [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) с каждым объявленным параметром. Это упрощает чтение кода.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Всегда существует потенциальный риск, позволяющий процедуре изменять значение, которое является базовым для аргумента в вызывающем коде. Убедитесь, что это значение было изменено, и будьте готовы проверить его на допустимость перед его использованием.  
  
## <a name="see-also"></a>См. также:

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
