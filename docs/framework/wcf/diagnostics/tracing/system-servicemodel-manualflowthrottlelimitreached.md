---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 35f149423fc8c0cd2a25834742d7c8b79ad8d8c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="a8444-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="a8444-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="a8444-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="a8444-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="a8444-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="a8444-104">Description</span></span>  
 <span data-ttu-id="a8444-105">Система достигла предела, заданного ограничителем ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="a8444-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="a8444-106">Значение регулировки, в зависимости от конкретного случая, может быть изменено с помощью изменения свойства ManualFlowControlLimit либо в классе ServiceHost, либо в классе InstanceContext.</span><span class="sxs-lookup"><span data-stu-id="a8444-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="a8444-107">Такая трассировка выдается, если ручной предел управления потоками первоначально снижается до 0.</span><span class="sxs-lookup"><span data-stu-id="a8444-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="a8444-108">Последующие изменения до 0 не трассируются.</span><span class="sxs-lookup"><span data-stu-id="a8444-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="a8444-109">Предел управления потоками в контексте экземпляра трассируется один раз для каждого контекста.</span><span class="sxs-lookup"><span data-stu-id="a8444-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8444-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a8444-110">See Also</span></span>  
 [<span data-ttu-id="a8444-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="a8444-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="a8444-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="a8444-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="a8444-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="a8444-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
