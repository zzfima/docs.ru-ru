---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: de0bdd9e5ab922b09249bf550fde745042be8e58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666759"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="0e2de-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="0e2de-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="0e2de-103">При попытке повторного использования подключения в пуле произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="0e2de-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="0e2de-104">По истечении заданного промежутка времени выполнена еще одна попытка.</span><span class="sxs-lookup"><span data-stu-id="0e2de-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0e2de-105">Описание</span><span class="sxs-lookup"><span data-stu-id="0e2de-105">Description</span></span>  
 <span data-ttu-id="0e2de-106">Данная информационная трассировка показывает, что при попытке повторного использования подключения в пуле произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="0e2de-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="0e2de-107">Ошибка могла произойти из-за несовместимости или неготовности подключения в пуле, либо того, что оно до сих пор активно.</span><span class="sxs-lookup"><span data-stu-id="0e2de-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="0e2de-108">Дополнительные попытки повторного использования другого подключения в пуле предпринимаются по истечении заданного промежутка времени, и если не найдено ни одного используемого подключения, создается новое подключение.</span><span class="sxs-lookup"><span data-stu-id="0e2de-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e2de-109">См. также</span><span class="sxs-lookup"><span data-stu-id="0e2de-109">See also</span></span>

- [<span data-ttu-id="0e2de-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="0e2de-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="0e2de-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="0e2de-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0e2de-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="0e2de-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
