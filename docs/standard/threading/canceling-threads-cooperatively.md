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
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 334cbcf8b4a888dbac5962c0fd668673e15e0e29
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="85f4c-102">Совместная отмена потоков</span><span class="sxs-lookup"><span data-stu-id="85f4c-102">Canceling Threads Cooperatively</span></span>
<span data-ttu-id="85f4c-103">До [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]платформа .NET Framework не предоставляла встроенных средств согласованной отмены потока после его запуска.</span><span class="sxs-lookup"><span data-stu-id="85f4c-103">Prior to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="85f4c-104">Тем не менее в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]можно использовать токены для отмены потоков так же, как и для отмены объектов <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> или запросов PLINQ.</span><span class="sxs-lookup"><span data-stu-id="85f4c-104">However, in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use cancellation tokens to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="85f4c-105">Хотя класс <xref:System.Threading.Thread?displayProperty=nameWithType> не обеспечивает встроенную поддержку токенов отмены, токен можно передать процедуре потока с помощью конструктора <xref:System.Threading.Thread>, принимающего делегат <xref:System.Threading.ParameterizedThreadStart>.</span><span class="sxs-lookup"><span data-stu-id="85f4c-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="85f4c-106">В следующем примере показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="85f4c-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="85f4c-107">См. также</span><span class="sxs-lookup"><span data-stu-id="85f4c-107">See Also</span></span>  
 [<span data-ttu-id="85f4c-108">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="85f4c-108">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
