---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df0f983d646ea89eeef338b9742843e9fa50487b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="c148f-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="c148f-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="c148f-103">При попытке повторного использования подключения в пуле произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="c148f-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="c148f-104">По истечении заданного промежутка времени выполнена еще одна попытка.</span><span class="sxs-lookup"><span data-stu-id="c148f-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c148f-105">Описание</span><span class="sxs-lookup"><span data-stu-id="c148f-105">Description</span></span>  
 <span data-ttu-id="c148f-106">Данная информационная трассировка показывает, что при попытке повторного использования подключения в пуле произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="c148f-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="c148f-107">Ошибка могла произойти из-за несовместимости или неготовности подключения в пуле, либо того, что оно до сих пор активно.</span><span class="sxs-lookup"><span data-stu-id="c148f-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="c148f-108">Дополнительные попытки повторного использования другого подключения в пуле предпринимаются по истечении заданного промежутка времени, и если не найдено ни одного используемого подключения, создается новое подключение.</span><span class="sxs-lookup"><span data-stu-id="c148f-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c148f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="c148f-109">See Also</span></span>  
 [<span data-ttu-id="c148f-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="c148f-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="c148f-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="c148f-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="c148f-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="c148f-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
