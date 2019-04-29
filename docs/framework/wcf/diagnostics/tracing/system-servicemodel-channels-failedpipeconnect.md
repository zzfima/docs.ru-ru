---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.date: 03/30/2017
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
ms.openlocfilehash: 472821d880433cd6a3292838a48bcb0b5bb34c43
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666739"
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a><span data-ttu-id="bd040-102">System.ServiceModel.Channels.FailedPipeConnect</span><span class="sxs-lookup"><span data-stu-id="bd040-102">System.ServiceModel.Channels.FailedPipeConnect</span></span>
<span data-ttu-id="bd040-103">Сбой попытки соединения с конечной точкой именованного канала.</span><span class="sxs-lookup"><span data-stu-id="bd040-103">An attempt to connect to the named pipe endpoint failed.</span></span> <span data-ttu-id="bd040-104">По истечении заданного промежутка времени выполнена еще одна попытка.</span><span class="sxs-lookup"><span data-stu-id="bd040-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bd040-105">Описание</span><span class="sxs-lookup"><span data-stu-id="bd040-105">Description</span></span>  
 <span data-ttu-id="bd040-106">Данная информационная трассировка показывает сбой соединения с конечной точкой именованного канала.</span><span class="sxs-lookup"><span data-stu-id="bd040-106">This informational trace indicates a failure to connect to a named pipe endpoint.</span></span> <span data-ttu-id="bd040-107">Возможная причина: не найдена или занята конечная точка именованного канала.</span><span class="sxs-lookup"><span data-stu-id="bd040-107">This could happen if the named pipe endpoint is not found or is busy.</span></span> <span data-ttu-id="bd040-108">Через короткие промежутки времени производится несколько дополнительных попыток, пока одна из них не будет успешной, или до истечения времени, заданного свойством OpenTimeout.</span><span class="sxs-lookup"><span data-stu-id="bd040-108">Additional attempts are made, each separated by a short amount of time, until one succeeds or the OpenTimeout expires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd040-109">См. также</span><span class="sxs-lookup"><span data-stu-id="bd040-109">See also</span></span>

- [<span data-ttu-id="bd040-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="bd040-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="bd040-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="bd040-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="bd040-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="bd040-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
