---
title: Объявление и вызов событий
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 6f4c303604f9cf55b4ecd500636e0d2772b6234c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345091"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Пошаговое руководство. Объявление и создание событий (Visual Basic)
В этом пошаговом руководстве показано, как объявить и вызвать события для класса с именем `Widget`. После выполнения этих действий может потребоваться прочитать сопутствующий раздел [Пошаговое руководство. Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), в которой показано, как использовать события из `Widget` объектов для предоставления сведений о состоянии в приложении.  
  
## <a name="the-widget-class"></a>Класс Widget  
 Предположим, что в момент, когда у вас есть `Widget` класс. Класс `Widget` содержит метод, выполнение которого может занять много времени, и вы хотите, чтобы приложение могло поместить какой-либо индикатор завершения.  
  
 Конечно, можно сделать так, чтобы объект `Widget` отображал диалоговое окно «процент завершения», но это диалоговое окно будет зависнуть в каждом проекте, где использовался класс `Widget`. Хорошим принципом проектирования объектов является предоставление приложению, использующему объект, обработку пользовательского интерфейса, если только цель объекта не заключается в управлении формой или диалоговым окном.  
  
 Целью `Widget` является выполнение других задач, поэтому лучше добавить событие `PercentDone` и позволить процедуре, вызывающей `Widget`методы, обменять это событие и отображать обновления состояния. Событие `PercentDone` может также предоставлять механизм отмены задачи.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Создание примера кода для этого раздела  
  
1. Откройте новый проект приложения Windows Visual Basic и создайте форму с именем `Form1`.  
  
2. Добавьте две кнопки и метку для `Form1`.  
  
3. Присвойте им имена, как показано в следующей таблице.  
  
    |Object|Свойство|Параметр|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Задача запуска|  
    |`Button2`|`Text`|Отмена|  
    |`Label`|`(Name)`, `Text`|Лблперцентдоне, 0|  
  
4. В меню **проект** выберите команду **Добавить класс** , чтобы добавить класс с именем `Widget.vb` в проект.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Объявление события для класса Widget  
  
- Используйте ключевое слово `Event` для объявления события в классе `Widget`. Обратите внимание, что событие может иметь `ByVal` и `ByRef` аргументов, как событие `PercentDone` `Widget`демонстрируется следующим образом:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Когда вызывающий объект получает событие `PercentDone`, аргумент `Percent` содержит процент завершенной задачи. Аргумент `Cancel` может иметь значение `True`, чтобы отменить метод, вызвавший событие.  
  
> [!NOTE]
> Аргументы событий можно объявлять точно так же, как аргументы процедур, со следующими исключениями: события не могут иметь `Optional` или `ParamArray` аргументов, а события не имеют возвращаемых значений.  
  
 Событие `PercentDone` вызывается методом `LongTask` класса `Widget`. `LongTask` принимает два аргумента: время, в течение которого метод должен выполнять работу, и минимальный интервал времени до приостановки `LongTask` для вызова события `PercentDone`.  
  
#### <a name="to-raise-the-percentdone-event"></a>Вызов события PercentDone  
  
1. Чтобы упростить доступ к свойству `Timer`, используемому этим классом, добавьте оператор `Imports` в верхнюю часть раздела объявлений модуля класса, над инструкцией `Class Widget`.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Добавьте следующий код в класс `Widget` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Когда приложение вызывает метод `LongTask`, класс `Widget` вызывает событие `PercentDone` каждые `MinimumInterval` секунд. При возвращении события `LongTask` проверяет, установлено ли для аргумента `Cancel` значение `True`.  
  
 Здесь требуется несколько отказов от ответственности. Для простоты `LongTask` процедура предполагает, что вы заранее понимаете, сколько времени займет задача. Это практически не так. Разделение задач на фрагменты даже размера может быть трудной задачей, и часто самое важное для пользователей — просто время, прошедшего до того, как получится, что что-то происходит.  
  
 Возможно, вы заметили другой изъян в этом примере. Свойство `Timer` возвращает число секунд, прошедших с полуночи; Поэтому приложение зависает, если оно запускается непосредственно перед полуночью. Более аккуратный подход к измерению времени приведет к рассмотрению таких условий, как это необходимо для рассмотрения, или избежать их вообще, используя такие свойства, как `Now`.  
  
 Теперь, когда класс `Widget` может создавать события, можно перейти к следующему пошаговому руководству. [Пошаговое руководство. Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) демонстрирует использование `WithEvents` для связывания обработчика событий с событием `PercentDone`.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Пошаговое руководство. Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
