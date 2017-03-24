---
title: "Практическое руководство: вызов обработчика событий в Visual Basic | Документы Microsoft"
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
- event handlers, calling
- event handlers
- procedures, event handlers
- procedures, calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
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
ms.openlocfilehash: c5b300feca3415d1283d24179795a4ae92c61e52
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Практическое руководство. Вызов обработчика событий в Visual Basic
*Событий* — это действие или условие — например мышью, щелчок или кредитный лимит превышение, которое распознается некоторым компонентом программы и для которого можно написать код для ответа. *Обработчик событий* является код, предназначенный для обработки события.  
  
 Обработчик событий в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] — `Sub` процедура. Тем не менее, не вызывается обычно он же так, как другие `Sub` процедур. Вместо этого необходимо определить процедуру в качестве обработчика для события. Это можно сделать с помощью [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложения и [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) переменной, или с [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). С помощью `Handles` предложение — по умолчанию способ объявления обработчика событий в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Этот способ записи обработчиков событий в конструкторах при программировании в интегрированную среду разработки (IDE). `AddHandler` Инструкция подходит для динамического создания событий во время выполнения.  
  
 При возникновении события, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически вызывает процедуру обработчика событий. Любой код, который имеет доступ к событию может привести к его выполнения, выполнив [оператор RaiseEvent](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 Можно связать несколько обработчиков событий с одним событием. В некоторых случаях можно отменить привязку обработчика события. Дополнительные сведения см. в разделе [события](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Для вызова обработчика событий с помощью WithEvents и метки  
  
1.  Убедитесь, что событие объявляется с [оператор Event](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2.  Объявите переменную объекта на уровне модуля или класса, уровня, с помощью [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) ключевое слово. `As` Предложение для этой переменной необходимо указать класс, который вызывает событие.  
  
3.  В объявлении обработки событий `Sub` процедуры добавления [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложение, определяющее `WithEvents` переменной и имя события.  
  
4.  При возникновении события, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически вызывает `Sub` процедуры. В коде можно использовать `RaiseEvent` инструкцию, чтобы создавать событие.  
  
     В следующем примере определяется событие и `WithEvents` переменную, которая ссылается на класс, который вызывает событие. Обработка событий `Sub` процедуры используется `Handles` предложение для указания класса и события, которые он обрабатывает.  
  
     [!code-vb[VbVbcnProcedures&#4;](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>Для вызова обработчика событий с помощью AddHandler  
  
1.  Убедитесь, что событие объявляется с `Event` инструкции.  
  
2.  Выполнение [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) для динамического связывания обработки события `Sub` процедуры с событием.  
  
3.  При возникновении события, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически вызывает `Sub` процедуры. В коде можно использовать `RaiseEvent` инструкцию, чтобы создавать событие.  
  
     В следующем примере определяется `Sub` процедура для обработки <xref:System.Windows.Forms.Form.Closing>события формы.</xref:System.Windows.Forms.Form.Closing> Затем он использует [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) для связывания `catchClose` процедуру как обработчик событий <xref:System.Windows.Forms.Form.Closing>.</xref:System.Windows.Forms.Form.Closing>  
  
     [!code-vb[VbVbcnProcedures&#5;](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     Обработчик событий из события можно отменить привязку, выполнив [оператор RemoveHandler](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Sub-процедуры](./sub-procedures.md)   
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Оператор AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Практическое руководство: создание процедуры](./how-to-create-a-procedure.md)   
 [Практическое руководство. Вызов процедуры, которая не возвращает значение](./how-to-call-a-procedure-that-does-not-return-a-value.md)
