---
title: "Практическое руководство. Вызов процедуры, которая не возвращает значение (Visual Basic) | Microsoft Docs"
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
  - "вызовы процедур, возвращаемые значения"
  - "процедуры, вызов"
  - "код Visual Basic, процедуры"
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Вызов процедуры, которая не возвращает значение (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Процедура `Sub` не возвращает значения в вызывающий код.  Ее вызов осуществляется явным образом в отдельном операторе.  Такую процедуру нельзя вызвать, просто указав ее имя в выражении.  
  
### Вызов процедуры Sub  
  
1.  Укажите имя процедуры `Sub`.  
  
2.  Запишите имя процедуры с заключенным в скобки списком аргументов.  Если не указано никаких аргументов, скобки можно опустить.  Тем не менее использование круглых скобок облегчает чтение кода.  
  
3.  Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.  Убедитесь что аргументы указаны в том же порядке, в каком в процедуре `Sub` определены соответствующие параметры.  
  
     В следующем примере вызывается функция [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> для активации окна приложения.  <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> принимает заголовок окна в качестве единственного аргумента.  Процедура не возвращает значения в вызывающий код.  Если программа "Блокнот" не запущена, в примере будет создано исключение <xref:System.ArgumentException>.  При выполнении процедуры `Shell` предполагается, что указанные пути соответствуют фактическим путям к приложениям.  
  
     [!code-vb[VbVbalrCatRef#11](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:System.ArgumentException>   
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Практическое руководство. Создание процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [Практическое руководство. Вызов процедуры, возвращающей значение](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)   
 [Практическое руководство. Вызов обработчика событий в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-event-handler.md)