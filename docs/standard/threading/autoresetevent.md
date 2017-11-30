---
title: AutoResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69d16e8c6491b4c66ab5a5452762e73172ebbb77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="autoresetevent"></a>AutoResetEvent
<xref:System.Threading.AutoResetEvent> Класс представляет событие дескриптора ожидания, которое сбрасывается автоматически при получении сигнала после освобождения одного ожидающего потока. Этот класс представляет специальное использование базового класса, <xref:System.Threading.EventWaitHandle>. Основную документацию по использованию и функциональным возможностям событий автоматического сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 <xref:System.Threading.AutoResetEvent> Сбрасывается автоматически несигнальное системой после выпуска одного ожидающего потока. Если ожидающих потоков нет, состояние объекта события остается сигнальным. <xref:System.Threading.AutoResetEvent>соответствует Win32 `CreateEvent` вызвать, указав `false` для `bManualReset` аргумент.  
  
 Пример, использующий <xref:System.Threading.AutoResetEvent>, в разделе [монитора](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Дескрипторы ожидания](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
