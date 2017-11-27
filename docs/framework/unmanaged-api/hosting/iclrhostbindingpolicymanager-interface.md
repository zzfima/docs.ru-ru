---
title: "Интерфейс ICLRHostBindingPolicyManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostBindingPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostBindingPolicyManager
helpviewer_keywords: ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eed5a72cb9da95f79831784d2bb53a6d60f92988
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="05753-102">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="05753-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="05753-103">Предоставляет методы для вычисления текущей политики привязки и сообщения изменений политики для указанной сборки узла.</span><span class="sxs-lookup"><span data-stu-id="05753-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05753-104">Методы</span><span class="sxs-lookup"><span data-stu-id="05753-104">Methods</span></span>  
  
|<span data-ttu-id="05753-105">Метод</span><span class="sxs-lookup"><span data-stu-id="05753-105">Method</span></span>|<span data-ttu-id="05753-106">Описание</span><span class="sxs-lookup"><span data-stu-id="05753-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05753-107">EvaluatePolicy-метод</span><span class="sxs-lookup"><span data-stu-id="05753-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="05753-108">Оценивает политику привязки от имени узла.</span><span class="sxs-lookup"><span data-stu-id="05753-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="05753-109">Modifyapplicationpolicy-метод</span><span class="sxs-lookup"><span data-stu-id="05753-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="05753-110">Изменяет политику привязки для указанной сборки и создает новую версию политики.</span><span class="sxs-lookup"><span data-stu-id="05753-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05753-111">Требования</span><span class="sxs-lookup"><span data-stu-id="05753-111">Requirements</span></span>  
 <span data-ttu-id="05753-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05753-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05753-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="05753-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05753-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="05753-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05753-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05753-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05753-116">См. также</span><span class="sxs-lookup"><span data-stu-id="05753-116">See Also</span></span>  
 [<span data-ttu-id="05753-117">Iclrassemblyidentitymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="05753-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="05753-118">IHostAssemblyStore-интерфейс</span><span class="sxs-lookup"><span data-stu-id="05753-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="05753-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="05753-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
