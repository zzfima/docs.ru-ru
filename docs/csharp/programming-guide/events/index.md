---
title: "События (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "классы [C#], события"
  - "язык C#, события"
  - "события [C#]"
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
caps.latest.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 43
---
# События (Руководство по программированию в C#)
События позволяют [классу](../../../csharp/language-reference/keywords/class.md) или объекту уведомлять другие классы или объекты о возникновении каких\-либо ситуаций. Класс, отправляющий \(или *порождающий*\) событие, называется *издателем*, а классы, принимающие \(или *обрабатывающие*\) событие, называются *подписчиками*.  
  
 В типичном веб\-приложении или приложении Windows Forms C\# вы подписываетесь на события, вызываемые элементами управления, такими как кнопки и списки. Вы можете использовать интегрированную среду разработки \(IDE\) [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)], чтобы просмотреть события, публикуемые элементом управления, и выбрать те из них, которые необходимо обработать. IDE автоматически добавляет пустой метод обработчика событий и код для подписки на событие. Для получения дополнительной информации см. [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## Общие сведения о событиях  
 События имеют следующие свойства:  
  
-   Издатель определяет, когда возникает событие; подписчики определяют, какое действие выполняется в ответ на событие.  
  
-   У события может быть несколько подписчиков. Подписчик может обрабатывать несколько событий от нескольких издателей.  
  
-   События, не имеющие подписчиков, никогда не возникают.  
  
-   Обычно события используются для оповещения о действиях пользователя, например нажатиях кнопок или выборе пунктов меню в графических пользовательских интерфейсах.  
  
-   Если событие имеет несколько подписчиков, при возникновении события обработчики событий вызываются синхронно. Сведения об асинхронном вызове событий см. в разделе [Calling Synchronous Methods Asynchronously](../Topic/Calling%20Synchronous%20Methods%20Asynchronously.md).  
  
-   В библиотеке классов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] события основываются на делегате <xref:System.EventHandler> и базовом классе <xref:System.EventArgs>.  
  
## Связанные разделы  
 Дополнительные сведения:  
  
-   [Практическое руководство. Подписка и отмена подписки на события](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [Практическое руководство. Публикация событий, соответствующих рекомендациям .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [Практическое руководство. Создание событий базового класса в производных классах](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [Синхронизация потоков](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md)  
  
-   [Практическое руководство. Использование словаря для хранения экземпляров событий](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [Практическое руководство. Реализация пользовательских методов доступа к событиям](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Главы в популярных книгах  
 [Делегаты, события и лямбда\-выражения](http://go.microsoft.com/fwlink/?LinkId=195395) в [справочном руководстве по C\# 3.0, третье издание: более 250 решений для программистов на C\# 3.0](http://go.microsoft.com/fwlink/?LinkId=195369)  
  
 [Делегаты и события](http://go.microsoft.com/fwlink/?LinkId=195418) в статье [Изучение C\# 3.0: овладение основными понятиями C\# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)  
  
## См. также  
 <xref:System.EventHandler>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)   
 [Creating Event Handlers in Windows Forms](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md)   
 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../Topic/Multithreaded%20Programming%20with%20the%20Event-based%20Asynchronous%20Pattern.md)