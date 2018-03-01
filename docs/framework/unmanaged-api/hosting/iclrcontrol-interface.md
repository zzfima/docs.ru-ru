---
title: "Интерфейс ICLRControl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b93d87107e1a69b0a047dbf156124fe49cd95d16
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="4f79c-102">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="4f79c-102">ICLRControl Interface</span></span>
<span data-ttu-id="4f79c-103">Предоставляет методы, позволяющие основному приложению получать ссылки на и настройки аспектов общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="4f79c-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f79c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4f79c-104">Methods</span></span>  
  
|<span data-ttu-id="4f79c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4f79c-105">Method</span></span>|<span data-ttu-id="4f79c-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="4f79c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f79c-107">Метод GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="4f79c-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="4f79c-108">Получает указатель интерфейса на экземпляр любого типа, который узел может использовать для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4f79c-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="4f79c-109">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="4f79c-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="4f79c-110">Задает тип, производный от <xref:System.AppDomainManager> как тип для диспетчеров доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="4f79c-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f79c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4f79c-111">Requirements</span></span>  
 <span data-ttu-id="4f79c-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f79c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f79c-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f79c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f79c-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f79c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f79c-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f79c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f79c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4f79c-116">See Also</span></span>  
 [<span data-ttu-id="4f79c-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="4f79c-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="4f79c-118">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="4f79c-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="4f79c-119">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="4f79c-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="4f79c-120">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4f79c-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="4f79c-121">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="4f79c-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="4f79c-122">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="4f79c-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="4f79c-123">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4f79c-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="4f79c-124">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="4f79c-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="4f79c-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4f79c-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
