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
ms.openlocfilehash: f70e7958cc9ac198738ed72732fe7b6563c89067
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970070"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="501b2-102">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="501b2-102">ICLRControl Interface</span></span>
<span data-ttu-id="501b2-103">Предоставляет методы, позволяющие узлу для получения ссылок на и настраивать параметры, среда CLR (CLR).</span><span class="sxs-lookup"><span data-stu-id="501b2-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="501b2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="501b2-104">Methods</span></span>  
  
|<span data-ttu-id="501b2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="501b2-105">Method</span></span>|<span data-ttu-id="501b2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="501b2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="501b2-107">Метод GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="501b2-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="501b2-108">Получает указатель интерфейса на экземпляр любого типа, который узел может использовать для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="501b2-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="501b2-109">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="501b2-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="501b2-110">Задает тип, производный от <xref:System.AppDomainManager> как тип для диспетчеров доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="501b2-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="501b2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="501b2-111">Requirements</span></span>  
 <span data-ttu-id="501b2-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="501b2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="501b2-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="501b2-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="501b2-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="501b2-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="501b2-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="501b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="501b2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="501b2-116">See also</span></span>

- [<span data-ttu-id="501b2-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="501b2-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="501b2-118">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="501b2-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="501b2-119">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="501b2-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="501b2-120">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="501b2-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="501b2-121">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="501b2-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="501b2-122">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="501b2-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="501b2-123">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="501b2-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="501b2-124">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="501b2-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="501b2-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="501b2-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
