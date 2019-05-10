---
title: Руководство по программированию на C#. События
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 8089219bc569e6c03a221871356bc70b0f1e57bb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595275"
---
# <a name="events-c-programming-guide"></a>События (Руководство по программированию в C#)
События позволяют [классу](../../../csharp/language-reference/keywords/class.md) или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций. Класс, отправляющий (или *порождающий*) событие, называется *издателем* , а классы, принимающие (или *обрабатывающие*) событие, называются *подписчиками*.  
  
 В типичном веб-приложении или приложении Windows Forms на C# вы подписываетесь на события, вызываемые элементами управления, такими как кнопки и списки. Вы можете использовать интегрированную среду разработки (IDE) Visual C#, чтобы просмотреть события, публикуемые элементом управления, и выбрать те из них, которые необходимо обрабатывать. IDE позволяет автоматически добавлять пустой метод обработчика событий и код для подписки на событие.  Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## <a name="events-overview"></a>Общие сведения о событиях  
 События имеют следующие свойства:  
  
- Издатель определяет, когда возникает событие; подписчики определяют, какое действие выполняется в ответ на событие.  
  
- У события может быть несколько подписчиков. Подписчик может обрабатывать несколько событий от нескольких издателей.  
  
- События, не имеющие подписчиков, никогда не возникают.  
  
- Обычно события используются для оповещения о действиях пользователя, например нажатиях кнопок или выборе пунктов меню в графических пользовательских интерфейсах.  
  
- Если событие имеет несколько подписчиков, при возникновении события обработчики событий вызываются синхронно. Сведения об асинхронном вызове событий см. в разделе [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
- В библиотеке классов [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] события основываются на делегате <xref:System.EventHandler> и базовом классе <xref:System.EventArgs> .  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
- [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
- [Практическое руководство. Публикация событий в соответствии с руководствами по .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
- [Практическое руководство. Создание событий базового класса в производных классах](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
- [Практическое руководство.  Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
- [Практическое руководство. Использование словаря для хранения экземпляров событий](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
- [Практическое руководство. Реализация пользовательских методов доступа к событиям](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  

Дополнительные сведения см. в разделе [События](~/_csharplang/spec/classes.md#events) в [Спецификации языка C#](../../language-reference/language-specification/index.md). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.
  
## <a name="featured-book-chapters"></a>Главы в популярных книгах  
 [Делегаты, события и лямбда-выражения](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) в [справочном руководстве по C# 3.0, третье издание. Более 250 решений для программистов на C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)  
  
 [Делегаты и события](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) в [изучении C# 3.0. Овладение основными понятиями C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)  
  
## <a name="see-also"></a>См. также

- <xref:System.EventHandler>
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Делегаты](../../../csharp/programming-guide/delegates/index.md)
- [Создание обработчиков событий в Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
