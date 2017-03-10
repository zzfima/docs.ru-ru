---
title: "Практическое руководство. Вызов обработчика событий в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "обработчики событий"
  - "обработчики событий, вызов"
  - "процедуры, вызов"
  - "процедуры, обработчики событий"
  - "код Visual Basic, процедуры"
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Практическое руководство. Вызов обработчика событий в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

*Событие* — это действие или условие \(например, щелчок мыши или превышение кредита\), которое распознается некоторым компонентом программы и для обработки которого можно написать код.  *Обработчик событий* — это код, предназначенный для обработки события.  
  
 Обработчик событий в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] — это процедура `Sub`.  Однако ее нельзя вызвать так же, как другие процедуры `Sub`.  Вместо этого необходимо определить процедуру в качестве обработчика для события.  Можно сделать это с помощью предложения [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) и переменной [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) или [Оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md).  Предложение `Handles` является способом объявления обработчика событий в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] по умолчанию.  В этом способе обработчики событий пишутся разработчиками в интегрированной среде разработки.  Оператор `AddHandler` подходит для динамического создания событий во время выполнения.  
  
 При возникновении события [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] автоматически вызывает процедуру обработчика событий.  Любой код, имеющий доступ к событию, может вызвать его выполнение с помощью [Оператор RaiseEvent](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 Можно связать несколько обработчиков событий с одним событием.  В некоторых случаях можно отменить привязку обработчика к событию.  Дополнительные сведения см. в разделе [События](../../../../visual-basic/programming-guide/language-features/events/events.md).  
  
### Вызов обработчика событий с помощью Handles и WithEvents  
  
1.  Убедитесь, что событие объявляется с помощью [Оператор Event](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2.  Объявите переменную объекта на уровне модуля или класса с помощью ключевого слова [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).  С помощью предложения `As` для этой переменной нужно указать класс, который вызывает событие.  
  
3.  В объявлении процедуры обработки события `Sub` добавьте предложение [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md), которое задает значение переменной `WithEvents` и имя события.  
  
4.  При возникновении события [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] автоматически вызывает процедуру `Sub`.  Код может использовать оператор `RaiseEvent`, чтобы создавать событие.  
  
     В следующем примере определяется событие и переменная `WithEvents`, которая ссылается на класс, который вызывает событие.  Процедура обработки события `Sub` использует предложение `Handles` для указания класса и события, которые он обрабатывает.  
  
     [!code-vb[VbVbcnProcedures#4](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-call-an-event-han_1.vb)]  
  
### Вызов обработчика событий с помощью AddHandler  
  
1.  Убедитесь, что событие объявлено с помощью оператора `Event`.  
  
2.  Выполните [Оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) для того, чтобы динамически связать процедуру обработки события `Sub` с событием.  
  
3.  При возникновении события [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] автоматически вызывает процедуру `Sub`.  Код может использовать оператор `RaiseEvent`, чтобы создавать событие.  
  
     В следующем примере определяется процедура `Sub` для обработки события формы <xref:System.Windows.Forms.Form.Closing>.  Затем используется [Оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md), чтобы связать процедуру `catchClose` в качестве обработчика событий для <xref:System.Windows.Forms.Form.Closing>.  
  
     [!code-vb[VbVbcnProcedures#5](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-call-an-event-han_2.vb)]  
  
     Можно отменить привязку обработчика к событию, выполнив [Оператор RemoveHandler](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Оператор AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Практическое руководство. Создание процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [Практическое руководство. Вызов процедуры, которая не возвращает значение](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)