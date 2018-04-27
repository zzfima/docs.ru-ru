---
title: Практическое руководство. Вызов обработчика событий в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b8a35459fdeb7cce0b494a9b3024a79bd4173cc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Практическое руководство. Вызов обработчика событий в Visual Basic
*Событий* — это действие или условие — например мыши щелчок или кредитный лимит превышение, которое распознается некоторым компонентом программы и для которого можно написать код для ответа. *Обработчик событий* — это код, предназначенный для обработки события.  
  
 Обработчик событий в Visual Basic — `Sub` процедура. Тем не менее, не вызывается обычно его же, как другие `Sub` процедуры. Вместо этого необходимо определить процедуру в качестве обработчика для события. Это можно сделать с помощью [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложение и [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) переменной, или с [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). С помощью `Handles` предложение — это способ объявления обработчика событий в Visual Basic по умолчанию. Это способ записи обработчиков событий в конструкторах при программировании в интегрированной среде разработки (IDE). `AddHandler` Инструкция подходит для динамического создания событий во время выполнения.  
  
 При возникновении события, Visual Basic автоматически вызывает процедуру обработчика событий. Любой код, который имеет доступ к событию может привести к его выполнения, выполнив [оператор RaiseEvent](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 С одним событием можно связать несколько обработчиков событий. В некоторых случаях можно отменить привязку обработчика события. Дополнительные сведения см. в статье [Events (Visual Basic)](../../../../visual-basic/programming-guide/language-features/events/index.md) (События в Visual Basic).  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Для вызова обработчика событий с помощью WithEvents и дескрипторов  
  
1.  Убедитесь, что событие объявляется с [оператор Event](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2.  Объявите переменную объекта на уровне модуля или класса уровня, с помощью [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) ключевое слово. `As` Предложение для этой переменной необходимо указать класс, который вызывает событие.  
  
3.  В объявлении обработки событий `Sub` процедуру, добавьте [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложение, определяющее `WithEvents` переменной и имя события.  
  
4.  При возникновении события, Visual Basic автоматически вызывает `Sub` процедуры. Код может использовать `RaiseEvent` инструкцию, чтобы создавать событие.  
  
     В следующем примере определяется событие и `WithEvents` переменную, которая ссылается на класс, который инициирует событие. Обработка событий `Sub` процедуры используется `Handles` предложений, чтобы указать класс и обрабатывает событие.  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>Для вызова обработчика событий с помощью AddHandler  
  
1.  Убедитесь, что событие объявляется с `Event` инструкции.  
  
2.  Выполнение [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) для динамического связывания обработки события `Sub` процедуры с событием.  
  
3.  При возникновении события, Visual Basic автоматически вызывает `Sub` процедуры. Код может использовать `RaiseEvent` инструкцию, чтобы создавать событие.  
  
     В следующем примере определяется `Sub` процедура будет обрабатывать <xref:System.Windows.Forms.Form.Closing> события формы. Затем он использует [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) связываемый `catchClose` процедуры в качестве обработчика событий для <xref:System.Windows.Forms.Form.Closing>.  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     Можно отменить привязку обработчика событий из события, выполнив [оператор RemoveHandler](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Подпрограммы](./sub-procedures.md)  
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Оператор AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Практическое руководство. Создание процедуры](./how-to-create-a-procedure.md)  
 [Практическое руководство. Вызов процедуры, которая не возвращает значение](./how-to-call-a-procedure-that-does-not-return-a-value.md)
