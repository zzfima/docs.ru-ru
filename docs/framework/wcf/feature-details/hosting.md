---
title: Hosting2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0820c7e5-0b50-4cde-80e7-74e346513002
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f25f0c9e773bbadd992284adf6c79d77aaa2441c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="hosting"></a><span data-ttu-id="0e955-102">Размещение</span><span class="sxs-lookup"><span data-stu-id="0e955-102">Hosting</span></span>
<span data-ttu-id="0e955-103">В подразделах этого раздела описано размещение служб.</span><span class="sxs-lookup"><span data-stu-id="0e955-103">The topics in the section describe service hosting.</span></span> <span data-ttu-id="0e955-104">Служба может размещаться Internet Information Services (IIS), служба активации Windows (WAS), Windows Server AppFabric, службе Windows или управляемом приложении — этот параметр часто называют *себя размещение*.</span><span class="sxs-lookup"><span data-stu-id="0e955-104">A service can be hosted by Internet Information Services (IIS), Windows Process Activation Service (WAS), Windows Server AppFabric, a Windows service, or by a managed application—this option is often referred to as *self hosting*.</span></span>  
  
 <span data-ttu-id="0e955-105">Важно отметить, что при запуске службы или любого расширения от недоверенного узла нарушается безопасность.</span><span class="sxs-lookup"><span data-stu-id="0e955-105">It is important to note that running a service or any extension from an untrusted host compromises security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e955-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0e955-106">In This Section</span></span>  
 [<span data-ttu-id="0e955-107">Размещение в службах IIS</span><span class="sxs-lookup"><span data-stu-id="0e955-107">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 <span data-ttu-id="0e955-108">Описывает способ [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] служба размещается в службах IIS или [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496).</span><span class="sxs-lookup"><span data-stu-id="0e955-108">Describes how a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service is hosted in Internet Information Services or [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496).</span></span>  
  
 [<span data-ttu-id="0e955-109">Размещение в службе активации процессов Windows</span><span class="sxs-lookup"><span data-stu-id="0e955-109">Hosting in Windows Process Activation Service</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)  
 <span data-ttu-id="0e955-110">Описывается размещение службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в службе активации Windows.</span><span class="sxs-lookup"><span data-stu-id="0e955-110">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted by Windows Process Activation Service.</span></span>  
  
 [<span data-ttu-id="0e955-111">Размещение в приложении службы Windows</span><span class="sxs-lookup"><span data-stu-id="0e955-111">Hosting in a Windows Service Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-windows-service-application.md)  
 <span data-ttu-id="0e955-112">Описывается размещение службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в службе Windows.</span><span class="sxs-lookup"><span data-stu-id="0e955-112">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted by a Windows service.</span></span>  
  
 [<span data-ttu-id="0e955-113">Размещение в управляемом приложении</span><span class="sxs-lookup"><span data-stu-id="0e955-113">Hosting in a Managed Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)  
 <span data-ttu-id="0e955-114">Описывается размещение службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в управляемом приложении.</span><span class="sxs-lookup"><span data-stu-id="0e955-114">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted in a managed application.</span></span>  
  
 [<span data-ttu-id="0e955-115">Активация на основе конфигурации в IIS и WAS</span><span class="sxs-lookup"><span data-stu-id="0e955-115">Configuration-Based Activation in IIS and WAS</span></span>](../../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)  
 <span data-ttu-id="0e955-116">Описывает, каким образом служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] размещается в IIS или WAS без использования SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="0e955-116">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted under IIS or WAS without using a .svc file.</span></span>  
  
 [<span data-ttu-id="0e955-117">Поддержка нескольких привязок узла IIS</span><span class="sxs-lookup"><span data-stu-id="0e955-117">Supporting Multiple IIS Site Bindings</span></span>](../../../../docs/framework/wcf/feature-details/supporting-multiple-iis-site-bindings.md)  
 <span data-ttu-id="0e955-118">Описывает, как задать несколько базовых адресов службы с помощью одной схемы URI для одного веб-узла.</span><span class="sxs-lookup"><span data-stu-id="0e955-118">Describes how to specify multiple base addresses for a service using the same URI scheme on a single Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e955-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0e955-119">See Also</span></span>  
 [<span data-ttu-id="0e955-120">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="0e955-120">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="0e955-121">Функции размещения Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="0e955-121">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
