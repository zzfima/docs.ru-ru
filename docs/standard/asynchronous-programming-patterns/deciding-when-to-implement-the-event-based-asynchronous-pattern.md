---
title: "Deciding When to Implement the Event-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "AsyncOperation class"
  - "AsyncCompletedEventArgs class"
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Deciding When to Implement the Event-based Asynchronous Pattern
Асинхронная модель, основанная на событиях, предоставляет модель предоставления асинхронного поведения класса.  При представлении этой модели [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] определяет две модели для представления асинхронного поведения: асинхронную модель, основанную на интерфейсе <xref:System.IAsyncResult?displayProperty=fullName>, и модель, основанную на событиях.  В этом разделе описаны случаи, в которых применима реализация обоих моделей.  
  
 Дополнительные сведения об асинхронном программировании с помощью интерфейса <xref:System.IAsyncResult> см. в разделе [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
## Общие принципы  
 В целом, следует предоставлять асинхронные функциональные возможности с помощью асинхронной модели, основанной на событиях, когда это возможно.  Однако существует ряд требований, которым модель, основанная на событиях, соответствовать не будет.  В этих случаях может понадобиться реализовать модель <xref:System.IAsyncResult> помимо модели, основанной на событиях.  
  
> [!NOTE]
>  Очень редко модель <xref:System.IAsyncResult> реализуется без реализации модели, основанной на событиях.  
  
## Рекомендации  
 В следующем списке описаны правила по реализации асинхронной модели, основанной на событиях:  
  
-   Используйте модель, основанную на событиях, в качестве интерфейса API по умолчанию для предоставления асинхронного поведения в классе.  
  
-   Не предоставляйте модель <xref:System.IAsyncResult>, если класс используется, в основном, в клиентском приложении, например в Windows Forms.  
  
-   Предоставляйте модель <xref:System.IAsyncResult> только в том случае, если это необходимо для выполнения требований.  Например, для совместимости с существующим API может потребоваться предоставление модели <xref:System.IAsyncResult>.  
  
-   Не предоставляйте модель <xref:System.IAsyncResult> без предоставления модели, основанной на событиях.  
  
-   Если необходимо предоставить модель <xref:System.IAsyncResult>, выполните это в качестве дополнительной возможности.  Например, если был создан объект прокси, создайте модель, основанную на событиях, по умолчанию с возможностью создания модели <xref:System.IAsyncResult>.  
  
-   Постройте собственную реализацию модели, основанной на событиях, для реализации модели <xref:System.IAsyncResult>.  
  
-   Избегайте предоставления модели, основанной на событиях, и модели <xref:System.IAsyncResult> в одном классе.  Предоставьте шаблон, основанный на событиях, в классах более высокого уровня, а шаблон <xref:System.IAsyncResult> — в классах более низкого уровня.  Например, сравните модель, основанную на событиях, в компоненте <xref:System.Net.WebClient> с моделью <xref:System.IAsyncResult> в классе <xref:System.Web.HttpRequest>.  
  
    -   Предоставьте модель, основанную на событиях, и модель <xref:System.IAsyncResult> для одного и того же класса, если это необходимо для совместимости.  Например, если интерфейс API, использующий модель <xref:System.IAsyncResult>, уже освобожден, необходимо оставить модель <xref:System.IAsyncResult> для обратной совместимости.  
  
    -   Предоставьте модель, на основе события, и модель <xref:System.IAsyncResult> для одного и того же класса, если сложность результирующей модели объекта превосходит преимущества разделения реализаций.  Лучше предоставить обе модели в одном классе, чем избегать предоставления модели, основанной на событиях.  
  
    -   Если необходимо предоставить обе модели <xref:System.IAsyncResult> и модели, основанной на событиях, используйте объект <xref:System.ComponentModel.EditorBrowsableAttribute>, заданный как <xref:System.ComponentModel.EditorBrowsableState>, для отметки реализации модели <xref:System.IAsyncResult> как дополнительной функциональной возможности.  Это указывает средам проектирования, таким как [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] IntelliSense, что не следует отображать свойства и методы <xref:System.IAsyncResult>.  Эти свойства и методы все еще можно использовать в полной мере, однако разработчик, работающий в IntelliSense, более ясно представляет интерфейс API.  
  
## Критерии предоставления модели IAsyncResult как дополнения к модели, основанной на событиях  
 Хотя асинхронная модель, основанная на событиях, имеет целый ряд преимуществ в сценариях, указанных выше, она содержит и ряд недостатков, о которых необходимо знать на тот случай, если производительность будет являться самым важным требованием.  
  
 Существует три случая, в которых модель, основанная на событиях, работает хуже, чем модель <xref:System.IAsyncResult>:  
  
-   Блокировка ожидания для одного объекта <xref:System.IAsyncResult>  
  
-   Блокировка ожидания на нескольких объектах <xref:System.IAsyncResult>  
  
-   Запрос завершения для объекта <xref:System.IAsyncResult>  
  
 В этих случаях можно использовать и модель, основанную на событиях, однако это будет более громоздким, чем использование модели <xref:System.IAsyncResult>.  
  
 Разработчики часто используют модель <xref:System.IAsyncResult> для служб, требования к производительности которых очень высоки.  Например, в случае запроса завершения используется высокопроизводительный сервер.  
  
 Кроме того, модель, основанная на событиях, менее эффективна по сравнению с моделью <xref:System.IAsyncResult>, так как создает большее количество объектов, особенно <xref:System.EventArgs>, и синхронизируется между потоками.  
  
 В следующем списке приведены некоторые рекомендации, которым стоит придерживаться, если необходимо использовать модель <xref:System.IAsyncResult>:  
  
-   Предоставляйте модель <xref:System.IAsyncResult>, только если напрямую необходима поддержка объектов <xref:System.Threading.WaitHandle> or <xref:System.IAsyncResult>.  
  
-   Предоставляйте шаблон <xref:System.IAsyncResult> только при наличии интерфейса API, который использует <xref:System.IAsyncResult>.  
  
-   Если имеется интерфейс API, основанный на модели <xref:System.IAsyncResult>, рассмотрите возможность предоставления модели, основанной на событиях, в следующем выпуске приложения.  
  
-   Предоставляйте модель <xref:System.IAsyncResult>, только если существуют требования к высокой производительности, которые не могут быть выполнены с помощью модели, основанной на событиях, а только с помощью модели <xref:System.IAsyncResult>.  
  
## См. также  
 [Walkthrough: Implementing a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)   
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)   
 [Implementing the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)   
 [Рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)