---
title: CountdownEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a>CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>Представляет примитив синхронизации, разблокирующий ожидающие потоки после ее сигнал определенное число раз. <xref:System.Threading.CountdownEvent>предназначен для сценариев, в которых в противном случае пришлось бы использовать <xref:System.Threading.ManualResetEvent> или <xref:System.Threading.ManualResetEventSlim> и вручную уменьшают значение переменной перед событием сигнализации. Например, в сценарии разветвления и соединения, можно просто создать <xref:System.Threading.CountdownEvent> со счетчиком сигналов, равным 5, а затем запустить пять рабочих элементов в потоке пула и каждого рабочего элемента вызова <xref:System.Threading.CountdownEvent.Signal%2A> до ее завершения. Каждый вызов <xref:System.Threading.CountdownEvent.Signal%2A> уменьшает значение счетчика на 1. В основном потоке вызов <xref:System.Threading.CountdownEvent.Wait%2A> будет блокироваться до счетчика равно нулю.  
  
> [!NOTE]
>  Для кода, не должны взаимодействовать с API синхронизации предыдущих версий .NET Framework, рассмотрите возможность использования <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> объектов или <xref:System.Threading.Tasks.Parallel.Invoke%2A> метода еще более простой подход к выражение параллелизма ветвления соединения.  
  
 <xref:System.Threading.CountdownEvent>предоставляет следующие дополнительные возможности.  
  
-   Операция ожидания может быть отменено с помощью токенов отмены.  
  
-   Значение счетчика может быть увеличен после создания экземпляра.  
  
-   Экземпляры можно использовать повторно после <xref:System.Threading.CountdownEvent.Wait%2A> возврата из метода <xref:System.Threading.CountdownEvent.Reset%2A> метод.  
  
-   Экземпляры предоставляют доступ <xref:System.Threading.WaitHandle> для интеграции с другими API синхронизации платформы .NET Framework такие как <xref:System.Threading.WaitHandle.WaitAll%2A>.  
  
## <a name="basic-usage"></a>Основное использование  
 В следующем примере демонстрируется использование <xref:System.Threading.CountdownEvent> с <xref:System.Threading.ThreadPool> рабочих элементов.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a>CountdownEvent отмены  
 В следующем примере показано, как отменить операции ожидания на <xref:System.Threading.CountdownEvent> с помощью токена отмены. Базовый шаблон действий следует модели универсальной отмены, который появился в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]. Дополнительные сведения см. в разделе [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md).  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 Обратите внимание, что операция ожидания не отменяет потоки, отправляющие сигналы. Как правило Отмена применяется к логической операции и, можно включить ожидание события, а также все рабочие элементы, синхронизация ожидания. В этом примере каждый рабочий элемент передается копия тот же токен отмены, чтобы он может ответить на запрос отмены.  
  
## <a name="see-also"></a>См. также  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
