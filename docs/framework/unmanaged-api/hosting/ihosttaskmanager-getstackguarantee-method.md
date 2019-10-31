---
title: Метод IHostTaskManager::GetStackGuarantee
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
ms.openlocfilehash: 22ec34c82d0f8e550dfc8941f2c048ebed6cf1d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133028"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="58765-102">Метод IHostTaskManager::GetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="58765-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="58765-103">Возвращает объем стекового пространства, который гарантированно будет доступен после завершения операции с стеком, но до закрытия процесса.</span><span class="sxs-lookup"><span data-stu-id="58765-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58765-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58765-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58765-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="58765-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="58765-106">заполняет Указатель на количество доступных байтов.</span><span class="sxs-lookup"><span data-stu-id="58765-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58765-107">Требования</span><span class="sxs-lookup"><span data-stu-id="58765-107">Requirements</span></span>  
 <span data-ttu-id="58765-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58765-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58765-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="58765-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58765-110">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="58765-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58765-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58765-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58765-112">См. также</span><span class="sxs-lookup"><span data-stu-id="58765-112">See also</span></span>

- [<span data-ttu-id="58765-113">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="58765-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
