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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a64f5885fd32d2486c90ebe4f8e0c739a025d0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="cc8d8-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="cc8d8-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>
<span data-ttu-id="cc8d8-103">Сбой попытки соединения с конечной точкой именованного канала.</span><span class="sxs-lookup"><span data-stu-id="cc8d8-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="cc8d8-104">По истечении заданного промежутка времени выполнена еще одна попытка.</span><span class="sxs-lookup"><span data-stu-id="cc8d8-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cc8d8-105">Описание</span><span class="sxs-lookup"><span data-stu-id="cc8d8-105">Description</span></span>  
 <span data-ttu-id="cc8d8-106">Данная информационная трассировка показывает сбой соединения с конечной точкой именованного канала.</span><span class="sxs-lookup"><span data-stu-id="cc8d8-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="cc8d8-107">Возможная причина: не найдена или занята конечная точка именованного канала.</span><span class="sxs-lookup"><span data-stu-id="cc8d8-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="cc8d8-108">Через короткие промежутки времени производится несколько дополнительных попыток, пока одна из них не будет успешной, или до истечения времени, заданного свойством OpenTimeout.</span><span class="sxs-lookup"><span data-stu-id="cc8d8-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc8d8-109">См. также</span><span class="sxs-lookup"><span data-stu-id="cc8d8-109">See Also</span></span>  
 [<span data-ttu-id="cc8d8-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="cc8d8-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="cc8d8-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="cc8d8-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="cc8d8-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="cc8d8-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
