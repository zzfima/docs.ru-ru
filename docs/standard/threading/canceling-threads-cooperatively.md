---
title: "Canceling Threads Cooperatively | Microsoft Docs"
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
  - "threads, cancellation"
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Canceling Threads Cooperatively
До [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] платформа .NET Framework не предоставляла встроенных средств согласованной отмены потока после его запуска. Однако в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] можно использовать токены для отмены потоков так же, как и для отмены объектов <xref:System.Threading.Tasks.Task?displayProperty=fullName> или запросов PLINQ. Хотя класс <xref:System.Threading.Thread?displayProperty=fullName> не обеспечивает встроенную поддержку токенов отмены, токен можно передать процедуре потока с помощью конструктора <xref:System.Threading.Thread>, принимающего делегат <xref:System.Threading.ParameterizedThreadStart>. В следующем примере показано, как это сделать.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## См. также  
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)