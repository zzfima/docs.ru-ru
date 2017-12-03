---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d1386d9ac7f58e4dd692bbca3ca3915bc3fe453f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="6a157-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="6a157-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>
<span data-ttu-id="6a157-103">Сбой попытки соединения с конечной точкой именованного канала.</span><span class="sxs-lookup"><span data-stu-id="6a157-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="6a157-104">По истечении заданного промежутка времени выполнена еще одна попытка.</span><span class="sxs-lookup"><span data-stu-id="6a157-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6a157-105">Описание</span><span class="sxs-lookup"><span data-stu-id="6a157-105">Description</span></span>  
 <span data-ttu-id="6a157-106">Данная информационная трассировка показывает сбой соединения с конечной точкой именованного канала.</span><span class="sxs-lookup"><span data-stu-id="6a157-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="6a157-107">Возможная причина: не найдена или занята конечная точка именованного канала.</span><span class="sxs-lookup"><span data-stu-id="6a157-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="6a157-108">Через короткие промежутки времени производится несколько дополнительных попыток, пока одна из них не будет успешной, или до истечения времени, заданного свойством OpenTimeout.</span><span class="sxs-lookup"><span data-stu-id="6a157-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a157-109">См. также</span><span class="sxs-lookup"><span data-stu-id="6a157-109">See Also</span></span>  
 [<span data-ttu-id="6a157-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="6a157-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="6a157-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="6a157-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="6a157-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="6a157-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
