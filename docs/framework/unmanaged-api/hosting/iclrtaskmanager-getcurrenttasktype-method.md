---
title: "Метод ICLRTaskManager::GetCurrentTaskType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager.GetCurrentTaskType
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f4c1114f4d90c10d8ca40b1b6fc6e071eff5b3f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="b4be0-102">Метод ICLRTaskManager::GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="b4be0-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="b4be0-103">Получает тип задачи, выполняемой в данный момент.</span><span class="sxs-lookup"><span data-stu-id="b4be0-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4be0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4be0-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4be0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4be0-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="b4be0-106">[out] Указатель на значение [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) перечисление, указывающее тип задачи, выполняемой в данный момент.</span><span class="sxs-lookup"><span data-stu-id="b4be0-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4be0-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b4be0-107">Requirements</span></span>  
 <span data-ttu-id="b4be0-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4be0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4be0-109">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4be0-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4be0-110">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4be0-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4be0-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4be0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4be0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b4be0-112">See Also</span></span>  
 [<span data-ttu-id="b4be0-113">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b4be0-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
