---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: 86d47ab0a83ff3e4a68bfa8ccf1349cf2b345b23
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597740"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="90bf2-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="90bf2-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="90bf2-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="90bf2-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="90bf2-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="90bf2-104">Description</span></span>  
 <span data-ttu-id="90bf2-105">Система достигла предела, заданного ограничителем ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="90bf2-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="90bf2-106">Значение регулировки, в зависимости от конкретного случая, может быть изменено с помощью изменения свойства ManualFlowControlLimit либо в классе ServiceHost, либо в классе InstanceContext.</span><span class="sxs-lookup"><span data-stu-id="90bf2-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="90bf2-107">Такая трассировка выдается, если ручной предел управления потоками первоначально снижается до 0.</span><span class="sxs-lookup"><span data-stu-id="90bf2-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="90bf2-108">Последующие изменения до 0 не трассируются.</span><span class="sxs-lookup"><span data-stu-id="90bf2-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="90bf2-109">Предел управления потоками в контексте экземпляра трассируется один раз для каждого контекста.</span><span class="sxs-lookup"><span data-stu-id="90bf2-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90bf2-110">См. также</span><span class="sxs-lookup"><span data-stu-id="90bf2-110">See also</span></span>
- [<span data-ttu-id="90bf2-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="90bf2-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="90bf2-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="90bf2-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="90bf2-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="90bf2-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
