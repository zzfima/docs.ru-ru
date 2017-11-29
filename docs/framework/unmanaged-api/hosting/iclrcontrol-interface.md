---
title: "Интерфейс ICLRControl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRControl
helpviewer_keywords: ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 98b41ea0062534d9e990a7fe366e8f746ae87f38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="4f68f-102">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="4f68f-102">ICLRControl Interface</span></span>
<span data-ttu-id="4f68f-103">Предоставляет методы, позволяющие основному приложению получать ссылки на и настройки аспектов общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="4f68f-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f68f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4f68f-104">Methods</span></span>  
  
|<span data-ttu-id="4f68f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4f68f-105">Method</span></span>|<span data-ttu-id="4f68f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4f68f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f68f-107">Getclrmanager-метод</span><span class="sxs-lookup"><span data-stu-id="4f68f-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="4f68f-108">Получает указатель интерфейса на экземпляр любого типа, который узел может использовать для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4f68f-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="4f68f-109">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="4f68f-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="4f68f-110">Задает тип, производный от <xref:System.AppDomainManager> как тип для диспетчеров доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="4f68f-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f68f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4f68f-111">Requirements</span></span>  
 <span data-ttu-id="4f68f-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f68f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f68f-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f68f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f68f-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f68f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f68f-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f68f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f68f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4f68f-116">See Also</span></span>  
 [<span data-ttu-id="4f68f-117">Iclrassemblyidentitymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4f68f-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="4f68f-118">Iclrdebugmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4f68f-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="4f68f-119">Iclrgcmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4f68f-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="4f68f-120">Iclrhostbindingpolicymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4f68f-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="4f68f-121">Iclrhostprotectionmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4f68f-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="4f68f-122">ICLROnEventManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4f68f-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="4f68f-123">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4f68f-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="4f68f-124">IHostControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4f68f-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="4f68f-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4f68f-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
