---
title: "Объявление и создание событий (Visual Basic) | Документы Microsoft"
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
- declarations, events
- events [Visual Basic], walkthroughs
- declaring events, walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events, walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
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
ms.openlocfilehash: 233673c1d42684b7caa9042d18fb341a1043a31b
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Пошаговое руководство. Объявление и создание событий (Visual Basic)
В этом пошаговом руководстве демонстрируется объявление и вызов событий для класса с именем `Widget`. После выполнения шагов, может потребоваться чтение сопутствующего раздела [Пошаговое руководство: обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), который показывает, как использовать события из `Widget` объектов для предоставления сведений о состоянии в приложении.  
  
## <a name="the-widget-class"></a>Класс мини-приложения  
 Предположим, что у вас есть `Widget` класса. Ваш `Widget` класс содержит метод, который может занять много времени для выполнения и приложение, чтобы иметь возможность создавать какой-то индикатор выполнения.  
  
 Конечно, можно также `Widget` объекта Показать диалоговое окно Процент завершения, но затем это диалоговое окно будет присутствовать в каждом проекте, использующем `Widget` класса. Хороший подход при разработке объекта — это передать приложению, использующему объект, обработку пользовательского интерфейса, если объект специально для управления формой или диалоговым окном.  
  
 Назначение `Widget` является для выполнения других задач, поэтому лучше добавить `PercentDone` событий и позволяют процедуры, которая вызывает `Widget`методы обработки, событий и отображаемое состояние обновлений. `PercentDone` Событий также могут предоставлять механизм отмены данной задачи.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Чтобы создать пример кода для этого раздела  
  
1.  Откройте новую [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] приложения Windows проект и создать форму с именем `Form1`.  
  
2.  Добавьте две кнопки и метку, которая `Form1`.  
  
3.  Присвойте имена объектам, как показано в следующей таблице.  
  
    |Объект|Свойство|Параметр|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Задача запуска|  
    |`Button2`|`Text`|Cancel|  
    |`Label`|`(Name)`, `Text`|lblPercentDone 0|  
  
4.  На **проекта** меню, выберите **добавить класс** добавить класс с именем `Widget.vb` в проект.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Чтобы объявить событие для класса Widget  
  
-   Используйте `Event` ключевое слово для объявления события в `Widget` класса. Обратите внимание, что событие может иметь `ByVal` и `ByRef` аргументов, как `Widget`в `PercentDone` демонстрирует событий:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#1;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 Когда вызывающий объект получает `PercentDone` событий, `Percent` аргумент содержит процент выполнения задачи. `Cancel` Аргументу присвоено `True` отменить метод, который вызвал событие.  
  
> [!NOTE]
>  Аргументы событий можно объявлять так же, как аргументы процедур, за несколькими исключениями: события не могут иметь `Optional` или `ParamArray` аргументы и события не имеют возвращаемых значений.  
  
 `PercentDone` Событие `LongTask` метод `Widget` класса. `LongTask`принимает два аргумента: продолжительность времени симулирования методом выполнения работы и минимальное время интервала перед `LongTask` будет приостановлен для создания `PercentDone` события.  
  
#### <a name="to-raise-the-percentdone-event"></a>Для вызова события PercentDone  
  
1.  Для упрощения доступа к `Timer` добавления свойств, используемых в этом классе `Imports` инструкции в начало раздела объявлений модуля класса, выше `Class Widget` инструкции.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#2;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  Добавьте следующий код в класс `Widget` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents&#3;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 Когда приложение вызывает метод `LongTask` метода `Widget` класса вызывает `PercentDone` событие каждый `MinimumInterval` секунд. При возвращении события `LongTask` проверяет `Cancel` значение аргумента `True`.  
  
 Здесь необходимы несколько отказ от ответственности. Для простоты `LongTask` предполагается продолжительность задачи известно заранее. Это не так. Разделение задания на равные части может вызвать трудности, и часто наиболее пользователям важно просто объем времени, которое проходит, прежде чем они появятся сведения о происходящем.  
  
 Можно найти еще один недостаток в этом образце. `Timer` Свойство возвращает количество секунд, прошедших с полуночи; таким образом, приложение зависает, если он запущен только до полуночи. Для более точного измерения времени будет принять это во внимание или избежать их вообще, такие как с помощью свойства `Now`.  
  
 Теперь, когда `Widget` класс может создавать события, можно переместить в следующем пошаговом руководстве. [Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) демонстрирует использование `WithEvents` для сопоставления обработчика событий с `PercentDone` событий.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>   
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A></xref:Microsoft.VisualBasic.DateAndTime.Now%2A>   
 [Пошаговое руководство: Обработка событий](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)   
 [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
