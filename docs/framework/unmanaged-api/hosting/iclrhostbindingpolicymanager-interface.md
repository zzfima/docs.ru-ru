---
title: Интерфейс ICLRHostBindingPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98a2978b440e0e72b3b4c1ac3065fbaf5d70e508
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666102"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="f489b-102">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f489b-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="f489b-103">Предоставляет методы для вычисления текущей политики привязки и сообщения изменений политики для указанной сборки узла.</span><span class="sxs-lookup"><span data-stu-id="f489b-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f489b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f489b-104">Methods</span></span>  
  
|<span data-ttu-id="f489b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f489b-105">Method</span></span>|<span data-ttu-id="f489b-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="f489b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f489b-107">Метод EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="f489b-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="f489b-108">Оценивает политику привязки от имени узла.</span><span class="sxs-lookup"><span data-stu-id="f489b-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="f489b-109">Метод ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="f489b-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="f489b-110">Изменяет политику привязки для указанной сборки и создает новую версию политики.</span><span class="sxs-lookup"><span data-stu-id="f489b-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f489b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f489b-111">Requirements</span></span>  
 <span data-ttu-id="f489b-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f489b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f489b-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f489b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f489b-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f489b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f489b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f489b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f489b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f489b-116">See also</span></span>
- [<span data-ttu-id="f489b-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="f489b-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f489b-118">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="f489b-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="f489b-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f489b-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
