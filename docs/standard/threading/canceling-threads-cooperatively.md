---
title: "Совместная отмена потоков"
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
helpviewer_keywords: threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 482f48b347af1a4f76231abcb15abc2f4dba168b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="canceling-threads-cooperatively"></a>Совместная отмена потоков
До [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]платформа .NET Framework не предоставляла встроенных средств согласованной отмены потока после его запуска. Однако в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], можно использовать токены отмены для отмены потоков так же, как их можно использовать для отмены <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> объектов или запросов PLINQ. Несмотря на то что <xref:System.Threading.Thread?displayProperty=nameWithType> класса не обеспечивает встроенную поддержку токенов отмены, токен можно передать процедуре потока с помощью <xref:System.Threading.Thread> конструктор, принимающий <xref:System.Threading.ParameterizedThreadStart> делегата. В следующем примере показано, как это сделать.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>См. также  
 [Использование потоков и работа с потоками](../../../docs/standard/threading/using-threads-and-threading.md)
