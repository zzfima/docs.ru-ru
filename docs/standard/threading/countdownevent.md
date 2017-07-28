---
title: "CountdownEvent | Microsoft Docs"
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
  - "synchronization primitives, CountdownEvent"
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=fullName> — это примитив синхронизации, разблокирующий ожидающие потоки после получения определенного числа сигналов.  <xref:System.Threading.CountdownEvent> предназначен для сценариев, в которых без него пришлось бы использовать <xref:System.Threading.ManualResetEvent> или <xref:System.Threading.ManualResetEventSlim> и вручную уменьшать значение переменной\-счетчика перед сигнализацией события.  Например, в сценарии разветвления и соединения можно просто создать <xref:System.Threading.CountdownEvent> со счетчиком сигналов, равным 5, а затем запустить пять рабочих элементов в пуле потоков, вызывая после завершения работы в каждом рабочем элементе метод <xref:System.Threading.CountdownEvent.Signal%2A>.  Каждый вызов метода <xref:System.Threading.CountdownEvent.Signal%2A> уменьшает значение счетчика на 1.  В главном потоке вызов метода <xref:System.Threading.CountdownEvent.Wait%2A> приведет к блокировке, которая будет длиться до тех пор, пока значение счетчика не будет равно нулю.  
  
> [!NOTE]
>  В коде, которому не приходится взаимодействовать с API синхронизации из предыдущих версий платформы .NET Framework, имеет смысл использовать объекты <xref:System.Threading.Tasks.Task?displayProperty=fullName> и метод <xref:System.Threading.Tasks.Parallel.Invoke%2A> для еще более простой реализации параллелизма в сценарии разветвления и соединения.  
  
 <xref:System.Threading.CountdownEvent> имеет ряд дополнительных возможностей:  
  
-   Операция ожидания может быть отменена с помощью токенов отмены.  
  
-   Значение счетчика можно увеличить после создания экземпляра класса.  
  
-   Экземпляры можно использовать повторно после возврата из метода <xref:System.Threading.CountdownEvent.Wait%2A>; для этого следует вызвать метод <xref:System.Threading.CountdownEvent.Reset%2A>.  
  
-   Экземпляры предоставляют доступ к <xref:System.Threading.WaitHandle> для интеграции с другими API синхронизации платформы .NET Framework, например <xref:System.Threading.WaitHandle.WaitAll%2A>.  
  
## Основы использования  
 В следующем примере показано использование объекта <xref:System.Threading.CountdownEvent> в сочетании с рабочими элементами <xref:System.Threading.ThreadPool>.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## CountdownEvent с отменой  
 В следующем примере показана отмена операции ожидания <xref:System.Threading.CountdownEvent> с помощью токена отмены.  Базовый шаблон действий следует модели универсальной отмены, представленной в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].  Для получения дополнительной информации см. [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 Обратите внимание, что операция ожидания не отменяет потоки, отправляющие сигналы.  Обычно отмена применяется к логической операции; сюда может относиться ожидание события, а также все рабочие элементы, которые синхронизируются с помощью ожидания.  В данном примере всем рабочим элементам передается копия токена отмены, чтобы они могли обработать запрос отмены.  
  
## См. также  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)