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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763364"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="f109f-102">Метод ICLRTaskManager::GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="f109f-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="f109f-103">Получает тип задачи, выполняемой в данный момент.</span><span class="sxs-lookup"><span data-stu-id="f109f-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f109f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f109f-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f109f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f109f-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="f109f-106">[out] Указатель на значение [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) перечисление, указывающее тип задачи, выполняемой в данный момент.</span><span class="sxs-lookup"><span data-stu-id="f109f-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f109f-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f109f-107">Requirements</span></span>  
 <span data-ttu-id="f109f-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f109f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f109f-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f109f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f109f-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f109f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f109f-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f109f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f109f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f109f-112">See also</span></span>

- [<span data-ttu-id="f109f-113">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f109f-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
