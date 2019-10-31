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
ms.openlocfilehash: 6ba7b7adc104db528293d77c3591370c6ce02c25
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128604"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="cbab4-102">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="cbab4-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="cbab4-103">Предоставляет методы, уведомляющие узел о действиях, выполняемых средой CLR в случае прерываний, времени ожидания или сбоев.</span><span class="sxs-lookup"><span data-stu-id="cbab4-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cbab4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cbab4-104">Methods</span></span>  
  
|<span data-ttu-id="cbab4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cbab4-105">Method</span></span>|<span data-ttu-id="cbab4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cbab4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cbab4-107">Метод OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="cbab4-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="cbab4-108">Уведомляет основное приложение о том, что среда CLR собирается выполнить действие по умолчанию, заданное вызовом метода [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) в ответ на прерывание потока или выгрузку <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="cbab4-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="cbab4-109">Метод OnFailure</span><span class="sxs-lookup"><span data-stu-id="cbab4-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="cbab4-110">Уведомляет основное приложение о том, что среда CLR собирается выполнить действие, заданное вызовом [ICLRPolicyManager:: сетактиононфаилуре](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) в ответ на выделение ресурсов или сбой при реорганизации.</span><span class="sxs-lookup"><span data-stu-id="cbab4-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="cbab4-111">Метод OnTimeout</span><span class="sxs-lookup"><span data-stu-id="cbab4-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="cbab4-112">Уведомляет основное приложение о том, что среда CLR собирается выполнить действие, заданное вызовом метода [ICLRPolicyManager:: сетактиононтимеаут](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) в ответ на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="cbab4-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cbab4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="cbab4-113">Requirements</span></span>  
 <span data-ttu-id="cbab4-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbab4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbab4-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cbab4-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cbab4-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cbab4-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cbab4-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbab4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbab4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cbab4-118">See also</span></span>

- [<span data-ttu-id="cbab4-119">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="cbab4-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="cbab4-120">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="cbab4-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="cbab4-121">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="cbab4-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="cbab4-122">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="cbab4-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="cbab4-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="cbab4-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
