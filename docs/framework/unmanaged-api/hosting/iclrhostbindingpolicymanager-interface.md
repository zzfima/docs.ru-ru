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
ms.openlocfilehash: e494bbbd08a77329b7b64816216e4bb2e1b724a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074200"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="a41d5-102">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a41d5-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="a41d5-103">Предоставляет методы для вычисления текущей политики привязки и сообщения изменений политики для указанной сборки узла.</span><span class="sxs-lookup"><span data-stu-id="a41d5-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a41d5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a41d5-104">Methods</span></span>  
  
|<span data-ttu-id="a41d5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a41d5-105">Method</span></span>|<span data-ttu-id="a41d5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a41d5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a41d5-107">Метод EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="a41d5-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="a41d5-108">Оценивает политику привязки от имени узла.</span><span class="sxs-lookup"><span data-stu-id="a41d5-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="a41d5-109">Метод ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="a41d5-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="a41d5-110">Изменяет политику привязки для указанной сборки и создает новую версию политики.</span><span class="sxs-lookup"><span data-stu-id="a41d5-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a41d5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a41d5-111">Requirements</span></span>  
 <span data-ttu-id="a41d5-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a41d5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a41d5-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a41d5-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a41d5-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a41d5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a41d5-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a41d5-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a41d5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a41d5-116">See also</span></span>

- [<span data-ttu-id="a41d5-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="a41d5-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a41d5-118">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="a41d5-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="a41d5-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="a41d5-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
