---
title: Как выполнить Вызов процедуры, которая не возвращает значение (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: f85c7a7edf4d05dc50166ad4f30080c2e595cf65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590647"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Как выполнить Вызов процедуры, которая не возвращает значение (Visual Basic)
Объект `Sub` процедура не возвращает значение вызывающему коду. Вызвать его напрямую с помощью отдельного вызывающего оператора. Его нельзя вызвать, просто указав ее имя в выражении.  
  
### <a name="to-call-a-sub-procedure"></a>Для вызова процедуры Sub  
  
1.  Укажите имя `Sub` процедуры.  
  
2.  После имени процедуры с помощью скобок, заключите список аргументов. Если аргументы не используются, скобки можно опустить. Тем не менее с помощью скобок делает код более удобным для чтения.  
  
3.  Поместите аргументы в списке аргументов в скобки, разделенные запятыми. Убедитесь, что аргументы указаны в том же порядке, `Sub` процедуры определены соответствующие параметры.  
  
     В следующем примере вызывается Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> функции для активации окна приложения. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> принимает заголовок окна в качестве единственного аргумента. Он не возвращает значение вызывающему коду. Если Блокнот не запущена, в примере создается исключение <xref:System.ArgumentException>. `Shell` Предполагается приложения находятся в указанных путей.  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Практическое руководство. Создание процедуры](./how-to-create-a-procedure.md)
- [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
- [Практическое руководство. Вызов обработчика событий в Visual Basic](./how-to-call-an-event-handler.md)
