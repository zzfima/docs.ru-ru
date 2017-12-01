---
title: "Определение, когда следует реализовать асинхронную модель, основанную на событиях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48de1b736c251a61a2ad34975c77bc2bca139626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a>Определение, когда следует реализовать асинхронную модель, основанную на событиях
В асинхронную модель на основе событий предоставляет шаблон для предоставления асинхронного поведения класса. С появлением этого шаблона [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] определяет две модели для представления асинхронного поведения: асинхронную модель, основанную на <xref:System.IAsyncResult?displayProperty=nameWithType> интерфейс и модель на основе событий. Описывается, когда это подходит для реализации обоих шаблонов.  
  
 Дополнительные сведения об асинхронном программировании с <xref:System.IAsyncResult> интерфейса см. в разделе [на основе событий асинхронного шаблона (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
## <a name="general-principles"></a>Общие принципы  
 Как правило можно предоставить асинхронные функции с помощью на основе событий асинхронного шаблона при возможности. Однако существуют некоторые требования, которые не соответствуют шаблон на основе событий. В таких случаях может потребоваться реализовать <xref:System.IAsyncResult> шаблон помимо шаблон на основе событий.  
  
> [!NOTE]
>  Редко <xref:System.IAsyncResult> шаблона для реализации без также реализован шаблон на основе событий.  
  
## <a name="guidelines"></a>Рекомендации  
 Ниже приводятся рекомендации по реализации асинхронной модели на основе событий.  
  
-   Используйте схему на основе событий API по умолчанию для предоставления асинхронного поведения класса.  
  
-   Не предоставляйте <xref:System.IAsyncResult> шаблона, если ваш класс в основном используется в клиентском приложении, например Windows Forms.  
  
-   Предоставляют только <xref:System.IAsyncResult> шаблона, когда это необходимо для выполнения требований. Например, совместимости с существующим API может потребоваться предоставление <xref:System.IAsyncResult> шаблон.  
  
-   Не предоставляйте <xref:System.IAsyncResult> шаблон без предоставления модели, основанной на событиях.  
  
-   Если необходимо предоставить <xref:System.IAsyncResult> шаблона, выполните это в качестве дополнительной возможности. Например, при создании прокси-объект, создать шаблон на основе событий, по умолчанию с возможностью создания <xref:System.IAsyncResult> шаблон.  
  
-   Постройте собственную реализацию модели, основанной вашей <xref:System.IAsyncResult> реализацию модели.  
  
-   Избегайте использования обоих шаблон на основе событий и <xref:System.IAsyncResult> шаблона в том же классе. Предоставлять шаблон на основе событий в классах «более высокого уровня» и <xref:System.IAsyncResult> на «более низкого уровня» классов шаблонов. Например, сравнить модели, основанной на <xref:System.Net.WebClient> компонент с <xref:System.IAsyncResult> шаблона на <xref:System.Web.HttpRequest> класса.  
  
    -   Предоставьте модель на основе событий и <xref:System.IAsyncResult> шаблон для одного класса, если это необходимо для совместимости. Например, если уже освобожден API, который использует <xref:System.IAsyncResult> шаблон, потребуется сохранить <xref:System.IAsyncResult> шаблон для обеспечения обратной совместимости.  
  
    -   Предоставьте модель на основе событий и <xref:System.IAsyncResult> шаблона для одного класса, если сложность результирующей модели объекта превосходит преимущества разделения реализаций. Лучше предоставить обе модели в одном классе, чем избегать предоставления шаблон на основе событий.  
  
    -   Если необходимо предоставить обе модели на основе событий и <xref:System.IAsyncResult> шаблон для одного класса, используйте <xref:System.ComponentModel.EditorBrowsableAttribute> значение <xref:System.ComponentModel.EditorBrowsableState.Advanced> пометить <xref:System.IAsyncResult> реализацию модели как дополнительные функции. Это значит, что сред разработки, таких как [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] IntelliSense, чтобы не отображать <xref:System.IAsyncResult> свойства и методы. Эти свойства и методы используются по-прежнему полностью, но разработчик, работающий в IntelliSense имеет более четкое представление API-интерфейса.  
  
## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a>Критерии для предоставления модели IAsyncResult, помимо модели, основанной на событиях  
 Хотя в асинхронную модель на основе событий имеет целый ряд преимуществ в сценариях, указанных выше, она имеет некоторые недостатки, которые следует иметь в виду при к самым важным требованием производительности.  
  
 Существуют три сценария, шаблон на основе событий не предусматривает а также <xref:System.IAsyncResult> шаблон:  
  
-   Блокировка ожидания для одного<xref:System.IAsyncResult>  
  
-   Блокировка ожидания на нескольких <xref:System.IAsyncResult> объектов  
  
-   Запрос завершения для<xref:System.IAsyncResult>  
  
 Эти сценарии можно обратиться, используя шаблон на основе событий, но при этом является более громоздким, чем использование <xref:System.IAsyncResult> шаблон.  
  
 Разработчики часто используют <xref:System.IAsyncResult> шаблон для служб, которые обычно имеют очень высокая производительность требования. Например опрос для завершения сценария методика высокой производительности сервера.  
  
 Кроме того, шаблон на основе событий является менее эффективным, чем <xref:System.IAsyncResult> шаблона, так как он создает несколько объектов, особенно <xref:System.EventArgs>, и синхронизируется по потокам.  
  
 Ниже приведены некоторые рекомендации для выполнения, если вы решили использовать <xref:System.IAsyncResult> шаблон:  
  
-   Предоставляют только <xref:System.IAsyncResult> шаблона, если напрямую необходима поддержка <xref:System.Threading.WaitHandle> или <xref:System.IAsyncResult> объектов.  
  
-   Предоставляют только <xref:System.IAsyncResult> шаблонов при наличии существующих API, который использует <xref:System.IAsyncResult> шаблон.  
  
-   При наличии существующих API на основе <xref:System.IAsyncResult> шаблона, рассмотрите возможность предоставления модели, основанной на событиях, в следующем выпуске.  
  
-   Предоставляют только <xref:System.IAsyncResult> шаблон, если у вас есть требования к высокой производительности, которые могут быть выполнены с помощью модели, основанной на событиях, а также могут быть выполнены с <xref:System.IAsyncResult> шаблон.  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство. Реализация компонента, поддерживающего асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Многопоточное программирование с использованием асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [Реализация асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 [Рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
