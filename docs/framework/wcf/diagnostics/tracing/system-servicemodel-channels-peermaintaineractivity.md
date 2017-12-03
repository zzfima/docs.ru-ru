---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71bcb16b89934f7f04cfd7d2f3c4b0ef3009dd78
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="79e91-102">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="79e91-102">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>
<span data-ttu-id="79e91-103">Модуль PeerMaintainer выполняет определенную операцию (подробности содержатся в теле сообщения трассировки).</span><span class="sxs-lookup"><span data-stu-id="79e91-103">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="79e91-104">Описание</span><span class="sxs-lookup"><span data-stu-id="79e91-104">Description</span></span>  
 <span data-ttu-id="79e91-105">Эта трассировка возникает в ходе различных операций модуля обслуживания PeerMaintainer.</span><span class="sxs-lookup"><span data-stu-id="79e91-105">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="79e91-106">PeerMaintainer - это внутренний компонент узла PeerNode.</span><span class="sxs-lookup"><span data-stu-id="79e91-106">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="79e91-107">Каждую минуту или каждые 32 полученных сообщения он отправляет соседним узлам сообщение LinkUtility со статистическими данными о том, сколько сообщений было принято/отправлено и сколько из них полезны (не дубликаты, не подделаны).</span><span class="sxs-lookup"><span data-stu-id="79e91-107">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="79e91-108">Это позволяет определить значение LinkUtility определенного соседнего узла.</span><span class="sxs-lookup"><span data-stu-id="79e91-108">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="79e91-109">Приблизительно каждые пять минут модуль обслуживания проверяет состояние соединений с соседними узлами.</span><span class="sxs-lookup"><span data-stu-id="79e91-109">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="79e91-110">Если количество соединений с соседними узлами превышает идеальное число, модуль обслуживания урезает наименее полезные соединения.</span><span class="sxs-lookup"><span data-stu-id="79e91-110">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="79e91-111">Если соединений недостаточно, модуль обслуживания приобретает новые соединения.</span><span class="sxs-lookup"><span data-stu-id="79e91-111">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e91-112">См. также</span><span class="sxs-lookup"><span data-stu-id="79e91-112">See Also</span></span>  
 [<span data-ttu-id="79e91-113">Трассировка</span><span class="sxs-lookup"><span data-stu-id="79e91-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="79e91-114">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="79e91-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="79e91-115">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="79e91-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
