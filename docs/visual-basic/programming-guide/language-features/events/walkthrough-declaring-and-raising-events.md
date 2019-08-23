---
title: Объявление и вызов событий (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 20e2b0efbf40597049c515134f408927f18d5603
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956338"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Пошаговое руководство. Объявление и вызов событий (Visual Basic)
В этом пошаговом руководстве показано, как объявить и вызвать `Widget`события для класса с именем. После выполнения этих действий может потребоваться прочитать сопутствующий раздел [пошаговое руководство. Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), которая показывает, как использовать события из `Widget` объектов для предоставления сведений о состоянии в приложении.  
  
## <a name="the-widget-class"></a>Класс Widget  
 Предположим, что в момент, когда у `Widget` вас есть класс. В `Widget` классе есть метод, выполнение которого может занять много времени, и вы хотите, чтобы приложение могло поместить какой-либо индикатор завершения.  
  
 Конечно, можно сделать `Widget` так, чтобы объект отображал диалоговое окно «процент завершения», но в каждом проекте, где использовался этот `Widget` класс, будет задержаться это диалоговое окно. Хорошим принципом проектирования объектов является предоставление приложению, использующему объект, обработку пользовательского интерфейса, если только цель объекта не заключается в управлении формой или диалоговым окном.  
  
 Целью `Widget` является выполнение других задач, поэтому лучше `PercentDone` добавить событие и позволить процедуре, вызывающей `Widget`методы, обменять это событие и отображать обновления состояния. `PercentDone` Событие может также предоставлять механизм отмены задачи.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Создание примера кода для этого раздела  
  
1. Откройте новый проект приложения Windows Visual Basic и создайте форму с именем `Form1`.  
  
2. Добавьте две кнопки и метку в `Form1`.  
  
3. Присвойте им имена, как показано в следующей таблице.  
  
    |Объект|Свойство.|Параметр|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Задача запуска|  
    |`Button2`|`Text`|Отмена|  
    |`Label`|`(Name)`, `Text`|Лблперцентдоне, 0|  
  
4. В меню **проект** выберите команду **Добавить класс** , чтобы добавить в проект класс `Widget.vb` с именем.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Объявление события для класса Widget  
  
- Используйте ключевое слово для объявления события `Widget` в классе. `Event` Обратите внимание, что событие `ByVal` может `ByRef` иметь аргументы и `Widget`, `PercentDone` как показано в описании события:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Когда вызывающий объект получает `PercentDone` событие `Percent` , аргумент содержит процент завершенной задачи. Аргумент может иметь `True` значение, чтобы отменить метод, вызвавший событие. `Cancel`  
  
> [!NOTE]
> Аргументы событий можно объявлять так же, как аргументы процедур, за исключением следующих: События не могут `Optional` иметь `ParamArray` аргументов или, а события не имеют возвращаемых значений.  
  
 Событие вызывается `LongTask` методом`Widget`класса. `PercentDone` `LongTask`принимает два аргумента: продолжительность времени, в течение которого метод должен выполнять работу, и минимальный интервал времени до `LongTask` приостановки для `PercentDone` вызова события.  
  
#### <a name="to-raise-the-percentdone-event"></a>Вызов события PercentDone  
  
1. Чтобы упростить доступ `Timer` к свойству, используемому этим классом, `Imports` добавьте оператор в верхнюю часть раздела объявлений модуля `Class Widget` класса, над оператором.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Добавьте следующий код в класс `Widget` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Когда приложение вызывает `LongTask` метод `Widget` , класс вызывает `PercentDone` событие каждые `MinimumInterval` секунды. При возвращении события проверяет `LongTask` , был `Cancel` ли аргумент установлен в `True`значение.  
  
 Здесь требуется несколько отказов от ответственности. Для простоты `LongTask` процедура предполагает, что вы заранее понимаете, сколько времени займет задача. Это практически не так. Разделение задач на фрагменты даже размера может быть трудной задачей, и часто самое важное для пользователей — просто время, прошедшего до того, как получится, что что-то происходит.  
  
 Возможно, вы заметили другой изъян в этом примере. `Timer` Свойство возвращает количество секунд, прошедших с полуночи, поэтому приложение зависает, если оно запускается непосредственно перед полуночью. Более аккуратный подход к измерению времени приведет к рассмотрению таких условий, как, например, с точки зрения, или избежать их `Now`вообще, используя такие свойства, как.  
  
 Теперь, `Widget` когда класс может создавать события, можно перейти к следующему пошаговому руководству. [Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) демонстрирует использование `WithEvents` для связывания обработчика событий с `PercentDone` событием.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
