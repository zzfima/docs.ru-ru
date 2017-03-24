---
title: "Практическое руководство: изменение значения аргумента процедуры (Visual Basic) | Документы Microsoft"
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
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 6c42a50b75bcc70ae0a3f70771b9e1f85626004b
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Практическое руководство. Изменение значения аргумента процедуры (Visual Basic)
При вызове процедуры каждый аргумент соответствует одному из параметров, определенных в процедуре. В некоторых случаях код процедуры можно изменить значение, лежащий в основе аргумента в вызывающем коде. В других случаях процедура может изменять только его локальную копию аргумента.  
  
 При вызове процедуры, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] делает локальную копию каждого аргумента, который передается [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Для каждого передаваемого аргумента [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет код процедуры прямую ссылку на программный элемент, лежащий в основе аргумента в вызывающем коде.  
  
 Если базовый элемент вызывающего кода является изменяемым, и аргумент передается `ByRef`, код процедуры позволяет изменить значение элемента в вызывающем коде прямых ссылок.  
  
## <a name="changing-the-underlying-value"></a>Изменение базового значения  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Чтобы изменить основное значение аргумента в вызывающем коде процедуры  
  
1.  В объявлении процедуры укажите [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для параметра, соответствующего аргументу.  
  
2.  В вызывающем коде передайте изменяемый элемент программирования в качестве аргумента.  
  
3.  В вызывающем коде не заключайте аргумент в список аргументов в скобках.  
  
4.  В коде процедуры используйте имя параметра для присвоения значения для базового элемента в вызывающем коде.  
  
 См. пример ниже, для демонстрации.  
  
## <a name="changing-local-copies"></a>Изменение локальных копий  
 Если базовый элемент в вызывающем коде является неизменяемым или аргумент передается `ByVal`, процедура не может изменять его значение в вызывающем коде. Однако процедура может изменить локальную копию такого аргумента.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>Чтобы изменить копию аргумента процедуры в коде процедуры  
  
1.  В объявлении процедуры укажите [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) для параметра, соответствующего аргументу.  
  
     -или-  
  
     В вызывающем коде заключите аргумент в списке аргументов в скобках. Это заставляет [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] передача аргумента по значению, даже если соответствующий параметр указывает `ByRef`.  
  
2.  В коде процедуры используйте имя параметра для присвоения значения локальной копии аргумента. Базовое значение в вызывающем коде не изменяется.  
  
## <a name="example"></a>Пример  
 Следующий пример показывает две процедуры, которые принимают переменную массива и производят на его элементы. `increase` Процедура просто добавляет единицу к каждому элементу. `replace` Процедура присваивает новый массив параметру `a()` и затем добавляет единицу к каждому элементу.  
  
 [!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#36;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 Первый `MsgBox` вызове отображается «после увеличения (n): 11, 21, 31, 41». Так как массив `n` является ссылочным типом, `replace` может изменить его элементы, несмотря на то, что механизм передачи `ByVal`.  
  
 Второй `MsgBox` вызове отображается «после замены(n): 101, 201, 301». Поскольку `n` передается `ByRef`, `replace` можно изменить переменную `n` в вызывающем коде и присвоить ей новый массив. Поскольку `n` является ссылочным типом, `replace` может изменять его члены.  
  
 Можно запретить процедуре изменять переменную в вызывающем коде. В разделе [как: защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Если переменная передается по ссылке, необходимо использовать `ByRef` ключевое слово для выбора этого способа.  
  
 По умолчанию в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] аргументы передаются по значению. Тем не менее, хорошим стилем программирования считается включают в себя [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром. Это облегчает чтение кода.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Всегда есть потенциальный риск при разрешении процедуре изменять значение базового аргумента в вызывающем коде. Убедитесь, что предполагается, что значение изменено и будьте готовы к проверке его допустимости перед его использованием.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)   
 [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)   
 [Различия между изменяемые и неизменяемые аргументы](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Практическое руководство: защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Практическое руководство: Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
