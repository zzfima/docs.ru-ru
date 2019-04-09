---
title: Метод ICLRTaskManager::GetCurrentTaskType
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2963e2a31fd62470e3ed6933edb38119d286071b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59071978"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="7dce3-102">Метод ICLRTaskManager::GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="7dce3-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="7dce3-103">Получает тип задачи, выполняемой в данный момент.</span><span class="sxs-lookup"><span data-stu-id="7dce3-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dce3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7dce3-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dce3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7dce3-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="7dce3-106">[out] Указатель на значение [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) перечисление, указывающее тип задачи, выполняемой в данный момент.</span><span class="sxs-lookup"><span data-stu-id="7dce3-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dce3-107">Требования</span><span class="sxs-lookup"><span data-stu-id="7dce3-107">Requirements</span></span>  
 <span data-ttu-id="7dce3-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dce3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dce3-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7dce3-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7dce3-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7dce3-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7dce3-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7dce3-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7dce3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7dce3-112">See also</span></span>

- [<span data-ttu-id="7dce3-113">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="7dce3-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
