---
title: "Практическое руководство: Принудительная передача аргумента по значению (Visual Basic) | Документы Microsoft"
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
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], in parentheses
- procedure arguments, in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
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
ms.openlocfilehash: eea3466534f1797170ae4bc72afbcba899929911
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Практическое руководство. Принудительная передача аргумента по значению (Visual Basic)
Объявление процедуры определяет механизм передачи. Если параметр объявляется [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ожидает передачи соответствующего аргумента по ссылке. Это позволяет процедуре изменять значение элемента программирования, содержащегося в аргументе в вызывающем коде. Если вы хотите защитить основные элементы от таких изменений, можно переопределить `ByRef` вызова механизм передачи в процедуре, заключив имя аргумента в скобки. Эти скобки являются дополнением к круглым скобкам, содержащим список аргументов в вызове.  
  
 Вызывающий код не может изменить [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) механизм.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Чтобы принудительно аргумент, передаваемый по значению  
  
-   Если соответствующий параметр объявлен `ByVal` в процедуре, не нужно предпринимать никаких дополнительных действий. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]уже ожидает передачи аргумента по значению.  
  
-   Если соответствующий параметр объявлен `ByRef` в процедуре, заключите аргумент в скобки в вызове процедуры.  
  
## <a name="example"></a>Пример  
 В следующем примере переопределяется `ByRef` объявление параметра. В вызове, требующем `ByVal`, обратите внимание на два уровня скобок.  
  
 [!code-vb[VbVbcnProcedures&#39;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#40;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 При `str` заключено в дополнительные скобки в списке аргументов, `setNewString` процедура не может изменять его значение в вызывающем коде и `MsgBox` отображает «Не может быть заменен при передаче ByVal». Когда `str` не заключен в дополнительные скобки процедуры можно изменить его, и `MsgBox` отображает «Это новое значение для аргумента inString».  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Если переменная передается по ссылке, необходимо использовать `ByRef` ключевое слово для выбора этого способа.  
  
 По умолчанию в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] аргументы передаются по значению. Тем не менее, хорошим стилем программирования считается включают в себя [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром. Это облегчает чтение кода.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если процедура объявляет параметр [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), правильное выполнение кода зависит от изменения базового элемента в вызывающем коде. Если код вызова переопределяет механизм вызова путем заключения аргумента в круглые скобки, или если он передает неизменяемого аргумента, процедура не может изменять базовый элемент. Это может привести к непредсказуемым результатам в вызывающем коде.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Всегда есть потенциальный риск при разрешении процедуре изменять значение базового аргумента в вызывающем коде. Убедитесь, что предполагается, что значение изменено и будьте готовы к проверке его допустимости перед его использованием.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)   
 [Различия между изменяемые и неизменяемые аргументы](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Практическое руководство: изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Практическое руководство: защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
