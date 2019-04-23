---
title: Интерфейс IHostPolicyManager
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9d903b4e44ea7a185ad8b3b71b7a5da2f2bda3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126351"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="f9204-102">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f9204-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="f9204-103">Предоставляет методы для уведомления узла действий, которые среда CLR (CLR) выполняет для прерываний, время ожидания или сбоев.</span><span class="sxs-lookup"><span data-stu-id="f9204-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9204-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f9204-104">Methods</span></span>  
  
|<span data-ttu-id="f9204-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f9204-105">Method</span></span>|<span data-ttu-id="f9204-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f9204-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f9204-107">Метод OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="f9204-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="f9204-108">Уведомляет основное приложение, среда CLR пытается выполнить действие по умолчанию, заданное с помощью вызова [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) в ответ на поток прервать или <xref:System.AppDomain> выгрузить.</span><span class="sxs-lookup"><span data-stu-id="f9204-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="f9204-109">Метод OnFailure</span><span class="sxs-lookup"><span data-stu-id="f9204-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="f9204-110">Уведомляет основное приложение, среда CLR пытается выполнить действие, заданное с помощью вызова [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) в ответ на сбой выделения и освобождения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f9204-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="f9204-111">Метод OnTimeout</span><span class="sxs-lookup"><span data-stu-id="f9204-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="f9204-112">Уведомляет основное приложение, среда CLR пытается выполнить действие, заданное с помощью вызова [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="f9204-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9204-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f9204-113">Requirements</span></span>  
 <span data-ttu-id="f9204-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9204-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9204-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f9204-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f9204-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9204-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9204-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9204-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9204-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f9204-118">See also</span></span>

- [<span data-ttu-id="f9204-119">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="f9204-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="f9204-120">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="f9204-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="f9204-121">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="f9204-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="f9204-122">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f9204-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="f9204-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f9204-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
