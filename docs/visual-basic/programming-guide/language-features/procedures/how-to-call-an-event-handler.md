---
title: Как вызвать обработчик событий
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 0c626a9ad92fe2cd0ea117a9abdd2965a09df2ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340429"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Практическое руководство. Вызов обработчика событий в Visual Basic

*Событие* — это действие или ситуация (например, превышение щелчка мыши или предела кредита), которые распознаются некоторым компонентом программы и для которых можно написать код для ответа. *Обработчик событий* — это код, который вы пишете для реагирования на событие.

 Обработчик событий в Visual Basic является процедурой `Sub`. Однако обычно он не вызывается так же, как другие `Sub` процедуры. Вместо этого вы определяете процедуру как обработчик для события. Это можно сделать с помощью предложения [Handles](../../../language-reference/statements/handles-clause.md) и переменной [WithEvents](../../../language-reference/modifiers/withevents.md) или с помощью [оператора AddHandler](../../../language-reference/statements/addhandler-statement.md). Использовать предложение `Handles` по умолчанию — это способ объявления обработчика событий в Visual Basic. Это способ, которым обработчики событий пишутся конструкторами при программировании в интегрированной среде разработки (IDE). Оператор `AddHandler` подходит для динамического вызова событий во время выполнения.

 Когда происходит событие, Visual Basic автоматически вызывает процедуру обработчика событий. Любой код, имеющий доступ к событию, может привести к его возникновению, выполнив [оператор RaiseEvent](../../../language-reference/statements/raiseevent-statement.md).

 Можно связать более одного обработчика событий с одним и тем же событием. В некоторых случаях можно отменить связь обработчика с событием. Дополнительные сведения см. в статье [Events (Visual Basic)](../events/index.md) (События в Visual Basic).

### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Вызов обработчика событий с помощью дескрипторов и WithEvents

1. Убедитесь, что событие объявлено с помощью [оператора Event](../../../language-reference/statements/event-statement.md).

2. Объявите переменную объекта на уровне модуля или класса с помощью ключевого слова [WithEvents](../../../language-reference/modifiers/withevents.md) . В предложении `As` для этой переменной должен быть указан класс, инициирующий событие.

3. В объявлении процедуры обработки событий `Sub` добавьте предложение [Handles](../../../language-reference/statements/handles-clause.md) , которое задает `WithEvents` переменную и имя события.

4. Когда происходит событие, Visual Basic автоматически вызывает процедуру `Sub`. В коде можно использовать инструкцию `RaiseEvent` для выполнения события.

     В следующем примере определяется событие и переменная `WithEvents`, которая ссылается на класс, который вызывает событие. Процедура `Sub` обработки событий использует предложение `Handles` для указания класса и события, которые он обрабатывает.

     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]

### <a name="to-call-an-event-handler-using-addhandler"></a>Вызов обработчика событий с помощью AddHandler

1. Убедитесь, что событие объявлено с помощью оператора `Event`.

2. Выполните [оператор AddHandler](../../../language-reference/statements/addhandler-statement.md) для динамического подключения процедуры обработки событий `Sub` с событием.

3. Когда происходит событие, Visual Basic автоматически вызывает процедуру `Sub`. В коде можно использовать инструкцию `RaiseEvent` для выполнения события.

     В следующем примере определяется процедура `Sub` для обработки события <xref:System.Windows.Forms.Form.Closing> формы. Затем в нем используется [оператор AddHandler](../../../language-reference/statements/addhandler-statement.md) , чтобы связать процедуру `catchClose` как обработчик событий для <xref:System.Windows.Forms.Form.Closing>.

     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]

     Можно отменить связь между обработчиком событий и событием, выполнив [оператор RemoveHandler](../../../language-reference/statements/removehandler-statement.md).

## <a name="see-also"></a>См. также

- [Процедуры](index.md)
- [Подпрограммы](sub-procedures.md)
- [Оператор Sub](../../../language-reference/statements/sub-statement.md)
- [Оператор AddressOf](../../../language-reference/operators/addressof-operator.md)
- [Практическое руководство. Создание процедуры](how-to-create-a-procedure.md)
- [Практическое руководство. Вызов процедуры, которая не возвращает значение](how-to-call-a-procedure-that-does-not-return-a-value.md)
