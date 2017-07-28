---
title: "События (Руководство по программированию на C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: b3f4673eccdbd568fa8ab042023a4b3bd8230bb3
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
<a id="events-c-programming-guide" class="xliff"></a>

# События (Руководство по программированию в C#)
События позволяют [классу](../../../csharp/language-reference/keywords/class.md) или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций. Класс, отправляющий (или *порождающий*) событие, называется *издателем* , а классы, принимающие (или *обрабатывающие*) событие, называются *подписчиками*.  
  
 В типичном веб-приложении или приложении Windows Forms C# вы подписываетесь на события, вызываемые элементами управления, такими как кнопки и списки. Вы можете использовать интегрированную среду разработки (IDE) [!INCLUDE[csprcs](~/includes/csprcs-md.md)], чтобы просмотреть события, публикуемые элементом управления, и выбрать те из них, которые необходимо обработать. IDE автоматически добавляет пустой метод обработчика событий и код для подписки на событие. Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
<a id="events-overview" class="xliff"></a>

## Общие сведения о событиях  
 События имеют следующие свойства:  
  
-   Издатель определяет, когда возникает событие; подписчики определяют, какое действие выполняется в ответ на событие.  
  
-   У события может быть несколько подписчиков. Подписчик может обрабатывать несколько событий от нескольких издателей.  
  
-   События, не имеющие подписчиков, никогда не возникают.  
  
-   Обычно события используются для оповещения о действиях пользователя, например нажатиях кнопок или выборе пунктов меню в графических пользовательских интерфейсах.  
  
-   Если событие имеет несколько подписчиков, при возникновении события обработчики событий вызываются синхронно. Сведения об асинхронном вызове событий см. в разделе [Calling Synchronous Methods Asynchronously](https://msdn.microsoft.com/library/2e08f6yc).  
  
-   В библиотеке классов [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] события основываются на делегате <xref:System.EventHandler> и базовом классе <xref:System.EventArgs>.  
  
<a id="related-sections" class="xliff"></a>

## Связанные разделы  
 Дополнительные сведения:  
  
-   [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [Практическое руководство. Публикация событий, соответствующих рекомендациям для .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [Практическое руководство. Создание событий базового класса в производных классах](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [Синхронизация потоков](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [Практическое руководство. Использование словаря для хранения экземпляров событий](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [Практическое руководство. Реализация пользовательских методов доступа к событиям](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
<a id="c-language-specification" class="xliff"></a>

## Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
<a id="featured-book-chapters" class="xliff"></a>

## Главы в популярных книгах  
 [Делегаты, события и лямбда-выражения](http://go.microsoft.com/fwlink/?LinkId=195395) в [справочном руководстве по C# 3.0, третье издание: более 250 решений для программистов на C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195369)  
  
 [Делегаты и события](http://go.microsoft.com/fwlink/?LinkId=195418) в статье [Изучение C# 3.0: овладение основными понятиями C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)  
  
<a id="see-also" class="xliff"></a>

## См. также  
 <xref:System.EventHandler>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)   
 [Создание обработчиков событий в Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx)   
 [Многопоточное программирование с использованием асинхронной модели на основе событий](https://msdn.microsoft.com/library/hkasytyf)
