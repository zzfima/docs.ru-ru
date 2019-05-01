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
ms.openlocfilehash: cab6c90947eae8abeb9387535eadb2f89e71454a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973094"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Пошаговое руководство. Объявление и вызов событий (Visual Basic)
В этом пошаговом руководстве демонстрируется объявление и вызов событий для класса с именем `Widget`. После выполнения действий, может потребоваться чтение сопутствующего раздела [Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), который показывает, как использовать события из `Widget` объекты, содержащие сведения о состоянии в приложении.  
  
## <a name="the-widget-class"></a>Класс мини-приложения  
 Предположим, у вас `Widget` класса. Ваш `Widget` класс имеет метод, который может занять много времени для выполнения, и требуется обновлять приложение, чтобы иметь возможность создавать какой-то индикатор выполнения.  
  
 Само собой, позволяющих улучшить `Widget` объект отображает процент завершения диалоговое окно, но затем это диалоговое окно будет присутствовать в каждом проекте, в котором использовались `Widget` класса. Хороший подход при разработке объекта — приложение, использующий дескриптор объекта пользовательского интерфейса, если объект специально для управления в форме или диалоговом окне.  
  
 Цель `Widget` является для выполнения других задач, поэтому лучше добавьте `PercentDone` событий, а также ускоряют выполнение процедуры, которая вызывает `Widget`в методы обрабатывают что обновляет состояние событий и отображения. `PercentDone` Событие также может предоставить механизм отмены задачи.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Для построения примера кода для этого раздела  
  
1. Откройте новый проект приложения Windows в Visual Basic и создайте форму с именем `Form1`.  
  
2. Добавьте две кнопки и метки для `Form1`.  
  
3. Присвойте им имена, как показано в следующей таблице.  
  
    |Объект|Свойство|Параметр|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Задача запуска|  
    |`Button2`|`Text`|Отмена|  
    |`Label`|`(Name)`, `Text`|lblPercentDone 0|  
  
4. На **проекта** меню, выберите **Добавление класса** добавляемый класс с именем `Widget.vb` в проект.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Для объявления события для класса мини-приложения  
  
- Используйте `Event` ключевого слова для объявления события в `Widget` класса. Обратите внимание, что событие может иметь `ByVal` и `ByRef` аргументы, как `Widget`в `PercentDone` демонстрирует событий:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Когда вызывающий объект получает `PercentDone` событий, `Percent` аргумент содержит процент завершения задачи. `Cancel` Аргумент может быть задан равным `True` отменить метод, который вызвал событие.  
  
> [!NOTE]
>  Аргументы событий можно объявлять так же, как аргументы процедур, за исключением следующих случаев: События не могут иметь `Optional` или `ParamArray` аргументов, а события не имеют возвращаемых значений.  
  
 `PercentDone` Событие `LongTask` метод `Widget` класса. `LongTask` принимает два аргумента: продолжительность времени метод симулирования выполнения работы и минимальный временной интервал перед `LongTask` приостанавливается, чтобы вызвать `PercentDone` событий.  
  
#### <a name="to-raise-the-percentdone-event"></a>Для вызова события PercentDone  
  
1. Для упрощения доступа к `Timer` добавьте свойство, используемое этим классом, `Imports` в начало раздела объявлений класса модуля, выше `Class Widget` инструкции.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Добавьте следующий код в класс `Widget` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Когда приложение вызывает `LongTask` метод, `Widget` формируемых классом `PercentDone` событий каждые `MinimumInterval` секунд. По возвращении из события `LongTask` проверяет, если `Cancel` значение аргумента `True`.  
  
 Здесь необходимы несколько заявления об отказе. Для простоты `LongTask` процедуре предполагается, заранее известно, сколько времени потребуется задачи. Это не так. Разделение задания на равные части может быть сложным, и часто наиболее важным для пользователей — это просто объем времени, которое проходит, прежде чем они появятся сведения о происходящем.  
  
 Возможно, Вы отметили еще один недостаток в этом образце. `Timer` Свойство возвращает количество секунд, прошедших с полуночи; таким образом, приложение зависает, если она запущена только до полуночи. Для более точного измерения времени будет принять это во внимание или избежать их в общей сложности с помощью свойств, таких как `Now`.  
  
 Теперь, когда `Widget` класс может создавать события, можно переместить в следующих пошаговых руководствах. [Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) демонстрирует использование `WithEvents` для связывания обработчика событий с `PercentDone` событий.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
