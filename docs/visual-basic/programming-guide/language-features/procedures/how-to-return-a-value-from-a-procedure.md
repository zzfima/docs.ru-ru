---
title: "Практическое руководство: возвращение значения из процедуры (Visual Basic) | Документы Microsoft"
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
- Visual Basic code, procedures
- procedures, returning from
- procedures, returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
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
ms.openlocfilehash: 98f0fb0740a021a16e87454bfaebbfad7858477c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Практическое руководство. Возврат значения из процедуры (Visual Basic)
Объект `Function` процедура возвращает значение в вызывающий код либо путем выполнения `Return` инструкции или путем добавления `Exit Function` или `End Function` инструкции.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Для возврата значения с помощью инструкции Return  
  
1.  Поместите `Return` инструкции в точку, где завершена задача процедуры.  
  
2.  Выполните `Return` ключевого слова и выражения, возвращающего значение требуется вернуться к вызывающему коду.  
  
3.  Можно иметь несколько `Return` инструкции в той же процедуре.  
  
     Следующие `Function` процедура вычисляет самая длинная сторона, гипотенуза прямоугольного треугольника и возвращается в вызывающий код.  
  
     [!code-vb[VbVbcnProcedures&#1;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     В следующем примере показано типичный вызов `hypotenuse`, который сохраняет возвращаемое значение.  
  
     [!code-vb[VbVbcnProcedures №&6;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Для возврата значения с помощью Exit Function или End Function  
  
1.  В по крайней мере в одном месте `Function` процедура, назначьте ему имя процедуры.  
  
2.  При выполнении `Exit Function` или `End Function` инструкции, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] возвращает значение, назначенное имени процедуры наиболее недавно.  
  
3.  Можно иметь несколько `Exit Function` инструкции в той же процедуре и можно смешивать `Return` и `Exit Function` инструкций в той же процедуре.  
  
4.  Можно иметь только одну `End Function` инструкции в `Function` процедуры.  
  
     Дополнительные сведения и пример см. в разделе «Возвращать значение» в [инструкции Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Sub-процедуры](./sub-procedures.md)   
 [Процедуры свойств](./property-procedures.md)   
 [Процедуры операторов](./operator-procedures.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Return](../../../../visual-basic/language-reference/statements/return-statement.md)   
 [Практическое руководство: создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md)   
 [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
