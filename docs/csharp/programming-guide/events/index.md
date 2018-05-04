---
title: События (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 5b844b20ac62b4cbc2a73931eecab95f22b4b1de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="events-c-programming-guide"></a>События (Руководство по программированию в C#)
События позволяют [классу](../../../csharp/language-reference/keywords/class.md) или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций. Класс, отправляющий (или *порождающий*) событие, называется *издателем* , а классы, принимающие (или *обрабатывающие*) событие, называются *подписчиками*.  
  
 В типичном веб-приложении или приложении Windows Forms C# вы подписываетесь на события, вызываемые элементами управления, такими как кнопки и списки. Вы можете использовать интегрированную среду разработки (IDE) Visual C#, чтобы просмотреть события, публикуемые элементом управления, и выбрать те из них, которые необходимо обрабатывать. IDE автоматически добавляет пустой метод обработчика событий и код для подписки на событие. Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## <a name="events-overview"></a>Общие сведения о событиях  
 События имеют следующие свойства:  
  
-   Издатель определяет, когда возникает событие; подписчики определяют, какое действие выполняется в ответ на событие.  
  
-   У события может быть несколько подписчиков. Подписчик может обрабатывать несколько событий от нескольких издателей.  
  
-   События, не имеющие подписчиков, никогда не возникают.  
  
-   Обычно события используются для оповещения о действиях пользователя, например нажатиях кнопок или выборе пунктов меню в графических пользовательских интерфейсах.  
  
-   Если событие имеет несколько подписчиков, при возникновении события обработчики событий вызываются синхронно. Сведения об асинхронном вызове событий см. в разделе [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
-   В библиотеке классов [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] события основываются на делегате <xref:System.EventHandler> и базовом классе <xref:System.EventArgs> .  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
-   [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [Практическое руководство. Публикация событий, соответствующих рекомендациям для .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [Практическое руководство. Создание событий базового класса в производных классах](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [Синхронизация потоков](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [Практическое руководство. Использование словаря для хранения экземпляров событий](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [Практическое руководство. Реализация пользовательских методов доступа к событиям](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a>Главы в популярных книгах  
 [Делегаты, события и лямбда-выражения](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) в [справочном руководстве по C# 3.0, третье издание: более 250 решений для программистов на C# 3.0](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)  
  
 [Делегаты и события](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) в статье [Изучение C# 3.0: овладение основными понятиями C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)  
  
## <a name="see-also"></a>См. также  
 <xref:System.EventHandler>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)  
 [Создание обработчиков событий в Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Многопоточное программирование с использованием асинхронной модели на основе событий](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
