---
title: "Практическое руководство. Возврат значения из процедуры (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce7aa0942be413986cb010963753447ea18cdf2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Практическое руководство. Возврат значения из процедуры (Visual Basic)
Объект `Function` процедура возвращает значение вызывающему коду либо выполнив `Return` инструкции или путем добавления `Exit Function` или `End Function` инструкции.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Для возврата значения с помощью инструкции Return  
  
1.  Поместите `Return` инструкции в той точке, где выполняется задача процедуры.  
  
2.  Выполните `Return` ключевое слово с помощью выражения, возвращающего значение, можно вернуться в вызывающий код.  
  
3.  В одной и той же процедуре можно использовать несколько операторов `Return`.  
  
     Следующие `Function` процедура рассчитывается длинной стороны, гипотенуза прямоугольного треугольника и возвращается в вызывающий код.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     В примере показан типичный вызов `hypotenuse`, который сохраняет возвращаемое значение.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Для возврата значения с помощью Exit Function или End Function  
  
1.  В по крайней мере в одном месте `Function` процедуры, назначить значение имени процедуры.  
  
2.  При выполнении `Exit Function` или `End Function` инструкции, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] возвращает значение, назначенное недавно имени процедуры.  
  
3.  В одной и той же процедуре можно использовать несколько операторов `Exit Function` и одновременно использовать операторы `Return` и `Exit Function`.  
  
4.  Может быть только один `End Function` инструкции в `Function` процедуры.  
  
     Дополнительные сведения и пример см. в разделе «Возвращение значения» в [Function, инструкция](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Подпрограммы](./sub-procedures.md)  
 [Процедуры свойств](./property-procedures.md)  
 [Процедуры операторов](./operator-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Return](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [Практическое руководство. Создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
