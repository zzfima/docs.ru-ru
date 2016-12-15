---
title: "Практическое руководство. Возврат значения из процедуры (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "процедуры, возвращаемое значение"
  - "процедуры, возврат из"
  - "код Visual Basic, процедуры"
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Возврат значения из процедуры (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Процедура `Function` возвращает значение вызывающему коду либо, выполняя инструкцию `Return`, либо при обнаружении инструкции `Exit Function` или `End Function`.  
  
### Возвращение значения с помощью инструкции Return  
  
1.  Поместите инструкцию `Return` в точку, где завершена задача процедуры.  
  
2.  Дополните ключевое слово `Return` выражением, представляющее собой значение, которое следует вернуть вызывающему коду.  
  
3.  В одной и той же процедуре допускается несколько инструкций `Return`.  
  
     В следующей процедуре `Function` рассчитывается самая длинная сторона \(гипотенуза\) прямоугольного треугольника и возвращается ее значение в вызывающий код.  
  
     [!code-vb[VbVbcnProcedures#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     В следующем примере показан типичный вызов `hypotenuse`, который сохраняет возвращаемое значение.  
  
     [!code-vb[VbVbcnProcedures#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### Возвращение значения с помощью Exit Function или End Function  
  
1.  Хотя бы в одном месте процедуры `Function` назначьте имени процедуры значение.  
  
2.  При выполнении инструкции `Exit Function` или инструкции `End Function` [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] возвращает самое последнее значение, назначенное имени процедуры.  
  
3.  В одной и той же процедуре можно использовать несколько инструкций `Exit Function`, кроме того, инструкции `Return` и `Exit Function` можно сочетать.  
  
4.  В процедуре `Function` допускается только одна инструкция `End Function`.  
  
     Дополнительные сведения и примеры содержатся в разделе "Возвращение значения" в [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Процедуры свойств](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Процедуры операторов](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Return](../../../../visual-basic/language-reference/statements/return-statement.md)   
 [Практическое руководство. Создание процедуры, возвращающей значение](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [Практическое руководство. Вызов процедуры, возвращающей значение](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)