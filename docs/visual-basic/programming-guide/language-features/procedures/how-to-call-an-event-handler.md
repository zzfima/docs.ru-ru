---
title: Практическое руководство. Вызов обработчика событий в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 3690d1c2eb8ece9059b8b25b5a14bef2021bc8f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864511"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Практическое руководство. Вызов обработчика событий в Visual Basic
*Событий* — это действие или условие, например мышью, щелчок или это кредитный лимит превышение, которое распознается некоторым компонентом программы и для которого можно написать код для реагирования. *Обработчик событий* — это код, предназначенный для ответа на событие.  
  
 Обработчик событий в Visual Basic — `Sub` процедуры. Тем не менее, вы обычно не вызывается он же так, как другие `Sub` процедуры. Вместо этого необходимо определить процедуру в качестве обработчика для события. Это можно сделать с помощью [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложение и [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) переменной, или с [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). С помощью `Handles` предложение является по умолчанию способ объявления обработчика событий в Visual Basic. Это способ записи обработчиков событий в конструкторах в интегрированной среде разработки (IDE). `AddHandler` Инструкция подходит для динамического создания событий во время выполнения.  
  
 При возникновении события, Visual Basic автоматически вызывает процедуру обработчика событий. Любой код, который имеет доступ к событию может привести к его выполнения, выполнив [оператор RaiseEvent](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 Можно связать несколько обработчиков событий с одним событием. В некоторых случаях можно отменить привязку обработчика события. Дополнительные сведения см. в статье [Events (Visual Basic)](../../../../visual-basic/programming-guide/language-features/events/index.md) (События в Visual Basic).  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Для вызова обработчика событий с помощью дескрипторы и WithEvents  
  
1. Убедитесь, что событие объявляется с [оператор Event](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2. Объявление объектной переменной в модуле или классе уровня, с помощью [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) ключевое слово. `As` Предложение для этой переменной необходимо указать класс, который вызывает событие.  
  
3. В объявлении обработки события `Sub` процедуру, добавьте [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложение, определяющее `WithEvents` переменной и имя события.  
  
4. При возникновении события, Visual Basic автоматически вызывает `Sub` процедуры. Код может использовать `RaiseEvent` инструкцию, чтобы создавать событие.  
  
     В следующем примере определяется событие и `WithEvents` переменную, которая ссылается на класс, который вызывает событие. Обработка событий `Sub` процедуры используется `Handles` предложение для указания класса и события, которые он обрабатывает.  
  
     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>Для вызова обработчика событий с помощью AddHandler  
  
1. Убедитесь, что событие объявляется с `Event` инструкции.  
  
2. Выполнение [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) динамически подключиться обработки события `Sub` процедуры с событием.  
  
3. При возникновении события, Visual Basic автоматически вызывает `Sub` процедуры. Код может использовать `RaiseEvent` инструкцию, чтобы создавать событие.  
  
     В следующем примере определяется `Sub` процедура будет обрабатывать <xref:System.Windows.Forms.Form.Closing> события формы. Затем он использует [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) связываемый `catchClose` процедуры в качестве обработчика событий для <xref:System.Windows.Forms.Form.Closing>.  
  
     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]  
  
     Обработчик событий из события можно отменить, выполнив [оператор RemoveHandler](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Подпрограммы](./sub-procedures.md)
- [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Оператор AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Практическое руководство. Создание процедуры](./how-to-create-a-procedure.md)
- [Практическое руководство. Вызов процедуры, которая не возвращает значение](./how-to-call-a-procedure-that-does-not-return-a-value.md)
