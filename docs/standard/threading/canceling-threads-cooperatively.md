---
title: Согласованная отмена потоков
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
ms.openlocfilehash: 1d1433ecf39974bf9e68fe07b9d0818ac16fb544
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138130"
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="cf279-102">Согласованная отмена потоков</span><span class="sxs-lookup"><span data-stu-id="cf279-102">Canceling threads cooperatively</span></span>

<span data-ttu-id="cf279-103">До версии 4 платформа .NET Framework не предоставляла встроенных средств для согласованной отмены потока после его запуска.</span><span class="sxs-lookup"><span data-stu-id="cf279-103">Prior to the .NET Framework 4, the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="cf279-104">Однако начиная с .NET Framework 4 вы можете использовать <xref:System.Threading.CancellationToken?displayProperty=nameWithType> для отмены потоков точно так же, как и для отмены объектов <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> или запросов PLINQ.</span><span class="sxs-lookup"><span data-stu-id="cf279-104">However, starting with the .NET Framework 4, you can use a <xref:System.Threading.CancellationToken?displayProperty=nameWithType> to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="cf279-105">Хотя класс <xref:System.Threading.Thread?displayProperty=nameWithType> не обеспечивает встроенную поддержку токенов отмены, токен можно передать процедуре потока с помощью конструктора <xref:System.Threading.Thread> , принимающего делегат <xref:System.Threading.ParameterizedThreadStart> .</span><span class="sxs-lookup"><span data-stu-id="cf279-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="cf279-106">В следующем примере показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="cf279-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="cf279-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cf279-107">See also</span></span>

- [<span data-ttu-id="cf279-108">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="cf279-108">Using Threads and Threading</span></span>](using-threads-and-threading.md)
