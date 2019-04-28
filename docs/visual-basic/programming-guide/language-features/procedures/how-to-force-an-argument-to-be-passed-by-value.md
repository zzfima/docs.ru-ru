---
title: Практическое руководство. Принудительная аргумента передаваться по значению (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 497ae11b858b7d164ba3b5607ff2109254a154de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863627"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Практическое руководство. Принудительная аргумента передаваться по значению (Visual Basic)
Объявление процедуры определяет механизм передачи. Если параметр объявлен [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic и ожидает передачи соответствующего аргумента по ссылке. Это позволяет процедуре для изменения значения элемента программирования, в аргументе в вызывающем коде. Если вы хотите защитить основные элементы от таких изменений, можно переопределить `ByRef` механизм передачи в процедуре вызовите, заключив имя аргумента в скобки. Эти скобки являются дополнением к круглым скобкам, содержащим список аргументов в вызове.  
  
 Вызывающий код не может переопределить [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) механизм.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Чтобы принудительно аргумент, передаваемый по значению  
  
- Если соответствующий параметр объявлен `ByVal` в процедуре, не нужно предпринимать дополнительные действия. Visual Basic уже ожидает передачи аргумента по значению.  
  
- Если соответствующий параметр объявлен `ByRef` в процедуре, заключите аргумент в круглые скобки в вызове процедуры.  
  
## <a name="example"></a>Пример  
 В следующем примере переопределяется `ByRef` объявление параметра. В вызове, требующем `ByVal`, обратите внимание на два уровня скобок.  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 Когда `str` заключен в дополнительные скобки в списке аргументов, `setNewString` процедура не может изменить его значение в вызывающий код, и `MsgBox` отображает «Не может быть заменен при передаче ByVal». При `str` не заключен в дополнительные скобки процедуру можно изменить его, и `MsgBox` отображает «Это новое значение для аргумента inString».  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Если переменная передается по ссылке, необходимо использовать `ByRef` ключевое слово, чтобы указать этот механизм.  
  
 По умолчанию в Visual Basic используется для передачи аргументов по значению. Тем не менее, рекомендуется использовать одну [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром. Это делает код более удобным для чтения.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если процедура объявляет параметр [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), правильное выполнение кода зависит от изменения базового элемента в вызывающем коде. Если вызывающий код переопределяет механизм вызова путем заключения аргумента в круглые скобки, или он передает неизменяемого аргумента, процедура не может изменять элемент. Это может привести к непредвиденным результатам в вызывающем коде.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Всегда найдется потенциальную угрозу в разрешении процедуре измените значение базового аргумента в вызывающем коде. Убедитесь, что предполагается, что это значение, чтобы изменить и будьте готовы, проверяемый на допустимость перед его использованием.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Различия между изменяемыми и неизменяемыми аргументами](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Практическое руководство. Изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)
- [Практическое руководство. Защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
