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
ms.openlocfilehash: 67bbf7bc95a0fe1ee8e9c2a6cf07d850d30bb028
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652813"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Пошаговое руководство. Объявление и создание событий (Visual Basic)
В этом пошаговом руководстве демонстрируется объявление и вызов событий для класса с именем `Widget`. После выполнения шагов можно ознакомиться с разделом дополнительное [Пошаговое руководство: обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), который показывает, как использовать события из `Widget` объектов для предоставления сведений о состоянии в приложении.  
  
## <a name="the-widget-class"></a>Класс мини-приложения  
 Предположим, что у вас есть `Widget` класса. Ваш `Widget` класс содержит метод, который может занять много времени для выполнения и приложение, чтобы иметь возможность создавать какой-то индикатор выполнения.  
  
 Конечно, может сделать `Widget` объект отображает диалоговое окно Процент завершения, но затем это диалоговое окно будет присутствовать в каждом проекте, использующем `Widget` класса. Хороший подход при разработке объекта — это передать приложению, использующему дескриптор объекта пользовательского интерфейса, если объект специально для управления формой или диалоговым окном.  
  
 Назначение `Widget` является выполнение других задач, поэтому рекомендуется добавить `PercentDone` событий и позволяют процедуры, которая вызывает `Widget`методы обработки, обновляет состояние события и отображения. `PercentDone` Событий также могут предоставлять механизм отмены задачи.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Для построения примера кода для этого раздела  
  
1.  Откройте новый проект приложения Windows в Visual Basic и создайте форму с именем `Form1`.  
  
2.  Добавьте две кнопки и метку для `Form1`.  
  
3.  Присвойте им имена, как показано в следующей таблице.  
  
    |Объект|Свойство|Параметр|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Задача запуска|  
    |`Button2`|`Text`|Отмена|  
    |`Label`|`(Name)`, `Text`|lblPercentDone 0|  
  
4.  На **проекта** меню, выберите **добавить класс** добавить класс с именем `Widget.vb` в проект.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Для объявления события для класса мини-приложения  
  
-   Используйте `Event` ключевое слово для объявления события в `Widget` класса. Обратите внимание, что событие может иметь `ByVal` и `ByRef` аргументы, как `Widget` `PercentDone` демонстрирует событий:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 Когда вызывающий объект получает `PercentDone` событий, `Percent` аргумент содержит процент завершения задачи. `Cancel` Аргумент может иметь значение `True` отменить метод, создавший событие.  
  
> [!NOTE]
>  Аргументы событий можно объявлять так же, как аргументы процедур, за следующими исключениями: события не могут иметь `Optional` или `ParamArray` аргументы и события не имеют возвращаемых значений.  
  
 `PercentDone` Событие `LongTask` метод `Widget` класса. `LongTask` принимает два аргумента: продолжительность времени симулирования методом выполнения работы и минимальный интервал времени перед `LongTask` приостанавливает свою работу, чтобы вызвать `PercentDone` событий.  
  
#### <a name="to-raise-the-percentdone-event"></a>Для вызова события PercentDone  
  
1.  Чтобы упростить доступ к `Timer` добавить свойства, используемого этим классом `Imports` инструкции в начало раздела объявлений модуля класса, выше `Class Widget` инструкции.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  Добавьте следующий код в класс `Widget` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 Когда приложение вызывает метод `LongTask` метода `Widget` формируемых классом `PercentDone` событие каждый `MinimumInterval` секунд. После завершения события, `LongTask` проверяет `Cancel` значение аргумента `True`.  
  
 Здесь необходимы несколько отказы от ответственности. Для простоты `LongTask` процедуре предполагается, как долго задачи известно заранее. Это не так. Разделение задания на равные части может быть сложным и часто наиболее пользователям важно просто объем времени, которое проходит, прежде чем они появятся сведения о происходящем.  
  
 Можно найти еще один недостаток в этом образце. `Timer` Свойство возвращает число секунд, прошедших с полуночи; таким образом, приложение зависает, если он запущен только до полуночи. Для более точного измерения времени бы принять это во внимание или избежать их вообще, такие как с помощью свойства `Now`.  
  
 Теперь, когда `Widget` класс может создавать события, можно переместить в следующем пошаговом руководстве. [Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) демонстрируется использование `WithEvents` для связывания обработчика событий с `PercentDone` событий.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>  
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
 [Пошаговое руководство. Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)  
 [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
