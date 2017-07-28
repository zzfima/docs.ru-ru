---
title: "Thread.Suspend, Garbage Collection, and Safe Points | Microsoft Docs"
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
  - "suspending threads"
  - "safe points"
  - "threading [.NET Framework], suspending"
  - "threading [.NET Framework], garbage collection"
  - "garbage collection, threads"
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Thread.Suspend, Garbage Collection, and Safe Points
Если для потока вызван метод <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>, система сообщает о поступившем запросе на приостановку потока и приостанавливает выполнение потока только после того, как он достигнет безопасной точки.  Безопасной точкой называется точка в выполнении потока, в которой может быть произведена сборка мусора.  
  
 По достижении этой точки приостановленный поток более не совершает никаких действий в управляемом коде.  Если поток выполняется вне управляемого кода, сборка мусора безопасна, и его выполнение продолжается до тех пор, пока им не будет произведена попытка восстановить выполнение управляемого кода.  
  
> [!NOTE]
>  Чтобы выполнить сборку мусора, среде выполнения необходимо приостановить все потоки кроме потока, отвечающего за сборку мусора.  Перед остановкой каждый поток должен достичь безопасной точки.  
  
## См. также  
 <xref:System.Threading.Thread>   
 <xref:System.GC>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Автоматическое управление памятью](../../../docs/standard/automatic-memory-management.md)