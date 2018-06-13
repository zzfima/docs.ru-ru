---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: a6b4e369d2d22d2441b3896321b7c152e21d967b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33483335"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="f7a12-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="f7a12-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="f7a12-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="f7a12-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="f7a12-104">Описание</span><span class="sxs-lookup"><span data-stu-id="f7a12-104">Description</span></span>  
 <span data-ttu-id="f7a12-105">Система достигла предела, заданного ограничителем ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="f7a12-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="f7a12-106">Значение регулировки, в зависимости от конкретного случая, может быть изменено с помощью изменения свойства ManualFlowControlLimit либо в классе ServiceHost, либо в классе InstanceContext.</span><span class="sxs-lookup"><span data-stu-id="f7a12-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="f7a12-107">Такая трассировка выдается, если ручной предел управления потоками первоначально снижается до 0.</span><span class="sxs-lookup"><span data-stu-id="f7a12-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="f7a12-108">Последующие изменения до 0 не трассируются.</span><span class="sxs-lookup"><span data-stu-id="f7a12-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="f7a12-109">Предел управления потоками в контексте экземпляра трассируется один раз для каждого контекста.</span><span class="sxs-lookup"><span data-stu-id="f7a12-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a12-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f7a12-110">See Also</span></span>  
 [<span data-ttu-id="f7a12-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="f7a12-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f7a12-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="f7a12-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f7a12-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="f7a12-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
