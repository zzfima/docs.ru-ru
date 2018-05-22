---
title: Совместная отмена потоков
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3edd0f9c991df8d8d70b14f4439c5c477e8f1401
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="canceling-threads-cooperatively"></a>Совместная отмена потоков
До [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]платформа .NET Framework не предоставляла встроенных средств согласованной отмены потока после его запуска. Тем не менее в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]можно использовать токены для отмены потоков так же, как и для отмены объектов <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> или запросов PLINQ. Хотя класс <xref:System.Threading.Thread?displayProperty=nameWithType> не обеспечивает встроенную поддержку токенов отмены, токен можно передать процедуре потока с помощью конструктора <xref:System.Threading.Thread>, принимающего делегат <xref:System.Threading.ParameterizedThreadStart>. В следующем примере показано, как это сделать.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>См. также  
 [Использование потоков и работа с потоками](../../../docs/standard/threading/using-threads-and-threading.md)
