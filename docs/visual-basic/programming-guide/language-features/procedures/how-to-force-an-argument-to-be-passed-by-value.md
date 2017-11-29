---
title: "Практическое руководство. Принудительная передача аргумента по значению (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fdb2df7e114f49c23db9f5b322ca9dd32135ac88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Практическое руководство. Принудительная передача аргумента по значению (Visual Basic)
Объявление процедуры определяет механизм передачи. Если параметр объявляется [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ожидает передачи соответствующего аргумента по ссылке. Это позволяет хранимой процедуре для изменения значения элемента программирования в аргументе в вызывающем коде. Если вы хотите защитить основные элементы от таких изменений, можно переопределить `ByRef` механизм передачи в процедуре вызовите, заключив имя аргумента в скобки. Эти скобки являются дополнением к круглым скобкам, содержащим список аргументов в вызове.  
  
 Вызывающий код не может переопределить [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) механизм.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Чтобы Принудительная передача аргумента по значению  
  
-   Если соответствующий параметр объявлен `ByVal` в процедуре, не требуется предпринимать дополнительные действия. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]уже ожидает передачи аргумента по значению.  
  
-   Если соответствующий параметр объявлен `ByRef` в процедуре, заключите аргумент в скобки в вызове процедуры.  
  
## <a name="example"></a>Пример  
 В следующем примере переопределяется `ByRef` объявление параметра. В вызове, требующем `ByVal`, обратите внимание на два уровня скобок.  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 Когда `str` заключается в дополнительные скобки в списке аргументов, `setNewString` процедура не может изменить его значение в вызывающем коде, и `MsgBox` отображает «Не может быть заменен при передаче ByVal». При `str` не заключен в лишние круглые скобки, процедура может изменять его, и `MsgBox` отображает «Это новое значение для аргумента inString».  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Если переменная передается по ссылке, необходимо использовать `ByRef` ключевое слово, чтобы указать этот механизм.  
  
 Значение по умолчанию в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] аргументы передаются по значению. Тем не менее, это хороший стиль программирования способ включения либо [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром. Это делает код более удобным для чтения.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если процедура объявляет параметр [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), правильное выполнение кода зависит от изменения базового элемента в вызывающем коде. Если вызывающий код переопределяет механизм вызова путем заключения аргумента в круглые скобки или прохождении неизменяемого аргумента, процедура не может изменять базовый элемент. Это может привести к непредсказуемым результатам в вызывающем коде.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Всегда есть потенциальный риск при разрешении процедуре изменять значение базового аргумента в вызывающем коде. Убедитесь, что предполагается, что это значение, чтобы изменить и будьте готовы к проверке его допустимости перед его использованием.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)  
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)  
 [Различия между изменяемыми и неизменяемыми аргументами](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Практическое руководство. Изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Практическое руководство. Защита аргумента процедуры от изменений значения](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)  
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
