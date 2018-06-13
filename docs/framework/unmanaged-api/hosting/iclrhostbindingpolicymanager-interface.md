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
ms.openlocfilehash: 637803c509935fdff080802f66f9f73ab8cf25e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431992"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="69c36-102">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="69c36-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="69c36-103">Предоставляет методы для вычисления текущей политики привязки и сообщения изменений политики для указанной сборки узла.</span><span class="sxs-lookup"><span data-stu-id="69c36-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69c36-104">Методы</span><span class="sxs-lookup"><span data-stu-id="69c36-104">Methods</span></span>  
  
|<span data-ttu-id="69c36-105">Метод</span><span class="sxs-lookup"><span data-stu-id="69c36-105">Method</span></span>|<span data-ttu-id="69c36-106">Описание</span><span class="sxs-lookup"><span data-stu-id="69c36-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69c36-107">Метод EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="69c36-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="69c36-108">Оценивает политику привязки от имени узла.</span><span class="sxs-lookup"><span data-stu-id="69c36-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="69c36-109">Метод ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="69c36-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="69c36-110">Изменяет политику привязки для указанной сборки и создает новую версию политики.</span><span class="sxs-lookup"><span data-stu-id="69c36-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69c36-111">Требования</span><span class="sxs-lookup"><span data-stu-id="69c36-111">Requirements</span></span>  
 <span data-ttu-id="69c36-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69c36-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69c36-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="69c36-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69c36-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69c36-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69c36-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69c36-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c36-116">См. также</span><span class="sxs-lookup"><span data-stu-id="69c36-116">See Also</span></span>  
 [<span data-ttu-id="69c36-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="69c36-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="69c36-118">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="69c36-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="69c36-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="69c36-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
