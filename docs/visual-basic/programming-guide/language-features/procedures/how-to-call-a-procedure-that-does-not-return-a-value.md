---
title: Практическое руководство. Вызов процедуры, которая не возвращает значение
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 3a5de98c6edf795a11bd9f0465aa6919f09eebfa
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340961"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Практическое руководство. Вызов процедуры, которая не возвращает значение (Visual Basic)
`Sub` процедура не возвращает значение в вызывающий код. Он вызывается явным образом с помощью изолированного вызывающего оператора. Его нельзя вызвать, просто используя его имя в выражении.  
  
### <a name="to-call-a-sub-procedure"></a>Вызов процедуры подпрограммы  
  
1. Укажите имя процедуры `Sub`.  
  
2. Чтобы заключить список аргументов, выполните имя процедуры с круглыми скобками. Если аргументы отсутствуют, можно дополнительно опустить круглые скобки. Однако использование круглых скобок упрощает чтение кода.  
  
3. Поместите аргументы в список аргументов в круглых скобках, разделяя их запятыми. Убедитесь, что аргументы указываются в том же порядке, в котором процедура `Sub` определяет соответствующие параметры.  
  
     В следующем примере вызывается функция Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> для активации окна приложения. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> принимает заголовок окна в качестве единственного аргумента. Он не возвращает значение в вызывающий код. Если процесс «Блокнот» не выполняется, в примере создается <xref:System.ArgumentException>. Процедура `Shell` предполагает, что приложения находятся в указанных путях.  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Практическое руководство. Создание процедуры](./how-to-create-a-procedure.md)
- [Практическое руководство. Вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md)
- [Как вызвать обработчик событий в Visual Basic](./how-to-call-an-event-handler.md)
