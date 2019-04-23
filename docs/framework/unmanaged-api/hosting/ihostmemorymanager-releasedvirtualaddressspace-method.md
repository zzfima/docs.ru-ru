---
title: Метод IHostMemoryManager::ReleasedVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0acbf4163e98b1171510260c4fac72c3d6f6fb1d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189291"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="4edd8-102">Метод IHostMemoryManager::ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="4edd8-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="4edd8-103">Уведомляет основное приложение завершение общеязыковой среды выполнения (CLR) с помощью указанной области памяти.</span><span class="sxs-lookup"><span data-stu-id="4edd8-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4edd8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4edd8-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4edd8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4edd8-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="4edd8-106">[in] Указатель на начальный адрес в памяти, которые будут выпущены.</span><span class="sxs-lookup"><span data-stu-id="4edd8-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4edd8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4edd8-107">Remarks</span></span>  
 <span data-ttu-id="4edd8-108">`ReleasedVirtualAddressSpace` Метод является методом обратного вызова и должны быть реализованы модулем записи ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="4edd8-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="4edd8-109">Он вызывается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="4edd8-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4edd8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4edd8-110">Requirements</span></span>  
 <span data-ttu-id="4edd8-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4edd8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4edd8-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4edd8-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4edd8-113">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4edd8-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4edd8-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4edd8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4edd8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4edd8-115">See also</span></span>

- [<span data-ttu-id="4edd8-116">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="4edd8-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
