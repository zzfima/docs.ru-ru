---
title: "Практическое руководство: вызов процедуры, возвращающей значение (Visual Basic) | Документы Microsoft"
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
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
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
ms.openlocfilehash: 17b2b902f3ee6ab79b2614b7742aa08fefab2420
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Практическое руководство. Вызов процедуры, которая не возвращает значение (Visual Basic)
A `Sub` процедура не возвращает значения в вызывающий код. Можно вызвать явным образом с помощью отдельного вызывающего оператора. Нельзя вызвать, просто указав ее имя в выражении.  
  
### <a name="to-call-a-sub-procedure"></a>Для вызова процедуры Sub  
  
1.  Укажите имя `Sub` процедуры.  
  
2.  После имени процедуры с заключенным в списке аргументов скобки. Если не указано никаких аргументов, скобки можно опустить. Однако с помощью скобок делает код более удобными для чтения.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, `Sub` процедуры определены соответствующие параметры.  
  
     В следующем примере вызывается [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>функцию для активации окна приложения.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>принимает в качестве единственного аргумента заголовок окна.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> Возвращает значение в вызывающий код. Если Блокнот не запущена, в примере возникает исключение <xref:System.ArgumentException>.</xref:System.ArgumentException> `Shell` Процедура предполагает приложения, в указанных путей.  
  
     [!code-vb[VbVbalrCatRef&11;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A></xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:System.ArgumentException></xref:System.ArgumentException>   
 [Процедуры](./index.md)   
 [Sub-процедуры](./sub-procedures.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Практическое руководство: создание процедуры](./how-to-create-a-procedure.md)   
 [Практическое руководство: вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)   
 [Практическое руководство: вызов обработчика событий в Visual Basic](./how-to-call-an-event-handler.md)
