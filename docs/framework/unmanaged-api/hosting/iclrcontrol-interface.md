---
title: Интерфейс ICLRControl
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a06c1f4e1fcfe9c9c361a0e0bb2e8722577a13b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="ea041-102">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="ea041-102">ICLRControl Interface</span></span>
<span data-ttu-id="ea041-103">Предоставляет методы, позволяющие основному приложению получать ссылки на и настройки аспектов общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="ea041-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ea041-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ea041-104">Methods</span></span>  
  
|<span data-ttu-id="ea041-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ea041-105">Method</span></span>|<span data-ttu-id="ea041-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ea041-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ea041-107">Метод GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="ea041-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="ea041-108">Получает указатель интерфейса на экземпляр любого типа, который узел может использовать для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ea041-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="ea041-109">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="ea041-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="ea041-110">Задает тип, производный от <xref:System.AppDomainManager> как тип для диспетчеров доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="ea041-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea041-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ea041-111">Requirements</span></span>  
 <span data-ttu-id="ea041-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea041-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea041-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ea041-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea041-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea041-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea041-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea041-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea041-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ea041-116">See Also</span></span>  
 [<span data-ttu-id="ea041-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="ea041-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="ea041-118">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="ea041-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="ea041-119">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="ea041-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="ea041-120">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="ea041-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="ea041-121">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="ea041-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="ea041-122">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="ea041-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="ea041-123">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="ea041-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="ea041-124">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="ea041-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="ea041-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="ea041-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
