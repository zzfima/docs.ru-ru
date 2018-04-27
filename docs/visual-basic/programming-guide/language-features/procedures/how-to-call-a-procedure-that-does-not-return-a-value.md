---
title: Практическое руководство. Вызов процедуры, которая не возвращает значение (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb9f13d5387f4a440a7fdd39c5e8f50cb8d56270
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Практическое руководство. Вызов процедуры, которая не возвращает значение (Visual Basic)
Объект `Sub` процедура не возвращает значение вызывающему коду. Она вызывается явным образом с помощью отдельного вызывающего оператора. Нельзя вызвать, просто указав ее имя в выражении.  
  
### <a name="to-call-a-sub-procedure"></a>Для вызова процедуры Sub  
  
1.  Укажите имя `Sub` процедуры.  
  
2.  После имени процедуры с помощью скобок, заключите список аргументов. Если не указано никаких аргументов, скобки можно опустить. Однако с помощью скобок делает код более удобным для чтения.  
  
3.  Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, `Sub` процедуры определены соответствующие параметры.  
  
     В следующем примере вызывается метод Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> функцию для активации окна приложения. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> принимает заголовок окна в качестве единственного аргумента. Возвращает значение вызывающему коду. Если Блокнот не запущена, в примере возникают исключения <xref:System.ArgumentException>. `Shell` Процедура предполагает приложения находятся в указанных путей.  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:System.ArgumentException>  
 [Процедуры](./index.md)  
 [Подпрограммы](./sub-procedures.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Практическое руководство. Создание процедуры](./how-to-create-a-procedure.md)  
 [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)  
 [Как: вызов обработчика событий в Visual Basic](./how-to-call-an-event-handler.md)
