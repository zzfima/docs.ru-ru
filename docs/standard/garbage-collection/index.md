---
title: "Сбор данных | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
caps.latest.revision: 36
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 11ea4186a77a600d1645fe334ba9fd704fe728b4
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="garbage-collection"></a>Сборка мусора
Сборщик мусора .NET управляет выделением и освобождением памяти для приложения. При каждом создании объекта среда CLR выделяет память для объекта из управляемой кучи. Пока в управляемой куче есть доступное адресное пространство, среда выполнения продолжает выделять пространство для новых объектов. Тем не менее ресурсы памяти не безграничны. В конечном счете сборщику мусора необходимо выполнить сбор, чтобы освободить память. Механизм оптимизации сборщика мусора определяет наилучшее время для выполнения сбора, основываясь на выполненных операциях выделения памяти. Когда сборщик мусора выполняет сборку, он проверяет наличие объектов в управляемой куче, которые больше не используются приложением, а затем выполняет необходимые операции, чтобы освободить память.  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Связанные разделы  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Основы сборки мусора](../../../docs/standard/garbage-collection/fundamentals.md)|Описание работы сборки мусора, выделения объектов в управляемой куче и других базовых понятий.|  
|[Сборка мусора и производительность](../../../docs/standard/garbage-collection/performance.md)|Проверки производительности, которые можно использовать для диагностики проблем со сборкой мусора и производительностью.|  
|[Индуцированные коллекции](../../../docs/standard/garbage-collection/induced.md)|Описание выполнения сборки мусора.|  
|[Режимы задержки](../../../docs/standard/garbage-collection/latency.md)|Описание режимов, которые определяют степень вмешательства сборщика мусора.|  
|[Оптимизация совместного размещения веб-сайтов](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|Способы оптимизации сборки мусора на серверах, совместно используемыми небольшими веб-узлами.|  
|[Уведомления о сборке мусора](../../../docs/standard/garbage-collection/notifications.md)|Определение необходимости полной сборки мусора и времени завершения этой операции.|  
|[Отслеживание ресурсов домена приложения](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|Способы наблюдения за использованием ЦП и памяти доменом приложения.|  
|[Слабые ссылки](../../../docs/standard/garbage-collection/weak-references.md)|Описание функциональных возможностей, которые позволяют сборщику мусора обрабатывать объект, разрешая при этом приложению получать доступ к этому объекту.|  
  
## <a name="reference"></a>Ссылка  
 <xref:System.GC?displayProperty=fullName>  
  
 <xref:System.GCCollectionMode?displayProperty=fullName>  
  
 <xref:System.GCNotificationStatus?displayProperty=fullName>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=fullName>  
  
 <xref:System.Runtime.GCSettings?displayProperty=fullName>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName>  
  
 <xref:System.Object.Finalize%2A?displayProperty=fullName>  
  
 <xref:System.IDisposable?displayProperty=fullName>  
  
## <a name="see-also"></a>См. также  
 [Очистка неуправляемых ресурсов](../../../docs/standard/garbage-collection/unmanaged.md)
