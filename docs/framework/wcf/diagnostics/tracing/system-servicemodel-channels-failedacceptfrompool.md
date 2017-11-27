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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e50e104816567927f53673f9b1da9c3c5beac3d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="2c872-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="2c872-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="2c872-103">При попытке повторного использования подключения в пуле произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="2c872-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="2c872-104">По истечении заданного промежутка времени выполнена еще одна попытка.</span><span class="sxs-lookup"><span data-stu-id="2c872-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2c872-105">Описание</span><span class="sxs-lookup"><span data-stu-id="2c872-105">Description</span></span>  
 <span data-ttu-id="2c872-106">Данная информационная трассировка показывает, что при попытке повторного использования подключения в пуле произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="2c872-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="2c872-107">Ошибка могла произойти из-за несовместимости или неготовности подключения в пуле, либо того, что оно до сих пор активно.</span><span class="sxs-lookup"><span data-stu-id="2c872-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="2c872-108">Дополнительные попытки повторного использования другого подключения в пуле предпринимаются по истечении заданного промежутка времени, и если не найдено ни одного используемого подключения, создается новое подключение.</span><span class="sxs-lookup"><span data-stu-id="2c872-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c872-109">См. также</span><span class="sxs-lookup"><span data-stu-id="2c872-109">See Also</span></span>  
 [<span data-ttu-id="2c872-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="2c872-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2c872-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="2c872-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2c872-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="2c872-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
