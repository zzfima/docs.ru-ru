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
ms.openlocfilehash: a9e090e83b180686ccb832aa6efb314c7e0fcc9a
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216618"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Практическое руководство. Вызов обработчика событий в Visual Basic

*Событие* — это действие или ситуация (например, превышение щелчка мыши или предела кредита), которые распознаются некоторым компонентом программы и для которых можно написать код для ответа. *Обработчик событий* — это код, который вы пишете для реагирования на событие.

 Обработчик событий в Visual Basic является `Sub` процедурой. Однако обычно он не вызывается так же, как другие `Sub` процедуры. Вместо этого вы определяете процедуру как обработчик для события. Это можно сделать с помощью предложения [Handles](../../../language-reference/statements/handles-clause.md) и переменной [WithEvents](../../../language-reference/modifiers/withevents.md) или с помощью [оператора AddHandler](../../../language-reference/statements/addhandler-statement.md). `Handles` Использование предложения по умолчанию является способом объявления обработчика событий в Visual Basic. Это способ, которым обработчики событий пишутся конструкторами при программировании в интегрированной среде разработки (IDE). `AddHandler` Оператор подходит для динамического вызова событий во время выполнения.

 Когда происходит событие, Visual Basic автоматически вызывает процедуру обработчика событий. Любой код, имеющий доступ к событию, может привести к его возникновению, выполнив [оператор RaiseEvent](../../../language-reference/statements/raiseevent-statement.md).

 Можно связать более одного обработчика событий с одним и тем же событием. В некоторых случаях можно отменить связь обработчика с событием. Дополнительные сведения см. в статье [Events (Visual Basic)](../events/index.md) (События в Visual Basic).

### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Вызов обработчика событий с помощью дескрипторов и WithEvents

1. Убедитесь, что событие объявлено с помощью [оператора Event](../../../language-reference/statements/event-statement.md).

2. Объявите переменную объекта на уровне модуля или класса с помощью ключевого слова [WithEvents](../../../language-reference/modifiers/withevents.md) . `As` Предложение для этой переменной должно указывать класс, который вызывает событие.

3. В объявлении процедуры обработки `Sub` событий добавьте `WithEvents` предложение [Handles](../../../language-reference/statements/handles-clause.md) , указывающее переменную и имя события.

4. Когда происходит событие, Visual Basic автоматически вызывает `Sub` процедуру. В коде можно использовать `RaiseEvent` инструкцию для выполнения события.

     В следующем примере определяется событие и `WithEvents` переменная, которая ссылается на класс, который вызывает событие. Процедура обработки `Sub` событий `Handles` использует предложение для указания класса и события, которые он обрабатывает.

     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]

### <a name="to-call-an-event-handler-using-addhandler"></a>Вызов обработчика событий с помощью AddHandler

1. Убедитесь, что событие объявлено с помощью `Event` оператора.

2. Выполните [оператор AddHandler](../../../language-reference/statements/addhandler-statement.md) , чтобы динамически подключить процедуру обработки `Sub` событий с событием.

3. Когда происходит событие, Visual Basic автоматически вызывает `Sub` процедуру. В коде можно использовать `RaiseEvent` инструкцию для выполнения события.

     В следующем примере определяется `Sub` процедура <xref:System.Windows.Forms.Form.Closing> обработки события формы. Затем он использует [оператор AddHandler](../../../language-reference/statements/addhandler-statement.md) , чтобы связать `catchClose` процедуру как обработчик событий для. <xref:System.Windows.Forms.Form.Closing>

     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]

     Можно отменить связь между обработчиком событий и событием, выполнив [оператор RemoveHandler](../../../language-reference/statements/removehandler-statement.md).

## <a name="see-also"></a>См. также

- [Процедуры](index.md)
- [Подпрограммы](sub-procedures.md)
- [Оператор Sub](../../../language-reference/statements/sub-statement.md)
- [Оператор AddressOf](../../../language-reference/operators/addressof-operator.md)
- [Практическое руководство. Создание процедуры](how-to-create-a-procedure.md)
- [Практическое руководство. Вызов процедуры, которая не возвращает значение](how-to-call-a-procedure-that-does-not-return-a-value.md)
