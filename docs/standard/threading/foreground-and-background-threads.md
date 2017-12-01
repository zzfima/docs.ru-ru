---
title: "Основные и фоновые потоки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ad427fc2c1175c0d9b333aa418aea039f11a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="foreground-and-background-threads"></a>Основные и фоновые потоки
Управляемый поток может в фоновом потоке или основной поток. Фоновые потоки идентичны основные потоки с одним исключением: фоновый поток не поддерживает хранение в управляемую среду выполнения под управлением. После управляемого процесса (где файл .exe — это управляемая сборка) были остановлены все основные потоки, система останавливает все фоновые потоки и завершает работу.  
  
> [!NOTE]
>  Когда среда выполнения останавливает фоновый поток, так как происходит отключение процесс, исключение не возникает в потоке. Тем не менее, когда потоки остановлены, так как <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> метод выгрузка домена приложения, <xref:System.Threading.ThreadAbortException> исключение в потоках переднего плана и фона.  
  
 Используйте <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> свойств, чтобы определить, является ли поток фоновый рисунок или основной поток, либо для изменения его статуса. Поток может изменяться в фоновый поток в любое время, задав его <xref:System.Threading.Thread.IsBackground%2A> свойства `true`.  
  
> [!IMPORTANT]
>  Основной или фоновой состояние потока не влияет на результат необработанное исключение в потоке. В платформе .NET Framework версии 2.0 необработанное исключение в обычном или фоновом режиме потоков приведет к завершению работы приложения. В разделе [исключения в управляемых потоках](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
 Потоки, относящиеся к группе управляемых потоков (то есть потоки которого <xref:System.Threading.Thread.IsThreadPoolThread%2A> свойство `true`) — это фоновые потоки. Все потоки, которые входят в управляемую среду выполнения из неуправляемого кода, помечаются как фоновые потоки. Все потоки, созданные путем создания и запуска нового <xref:System.Threading.Thread> объекта, по умолчанию переднего плана.  
  
 При использовании потока для отслеживания деятельности, такие как подключения через сокет, задать его <xref:System.Threading.Thread.IsBackground%2A> свойства `true` , чтобы поток не запрещает процесс завершается.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
