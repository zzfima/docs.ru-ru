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
ms.openlocfilehash: 1b7bf2a3e359ca05a147553d89a1d2bb3d235209
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571053"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="78e6f-102">Метод IHostMemoryManager::ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="78e6f-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="78e6f-103">Уведомляет основное приложение завершение общеязыковой среды выполнения (CLR) с помощью указанной области памяти.</span><span class="sxs-lookup"><span data-stu-id="78e6f-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78e6f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78e6f-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78e6f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78e6f-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="78e6f-106">[in] Указатель на начальный адрес в памяти, которые будут выпущены.</span><span class="sxs-lookup"><span data-stu-id="78e6f-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78e6f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="78e6f-107">Remarks</span></span>  
 <span data-ttu-id="78e6f-108">`ReleasedVirtualAddressSpace` Метод является методом обратного вызова и должны быть реализованы модулем записи ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="78e6f-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="78e6f-109">Он вызывается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="78e6f-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78e6f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="78e6f-110">Requirements</span></span>  
 <span data-ttu-id="78e6f-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78e6f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78e6f-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="78e6f-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78e6f-113">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="78e6f-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78e6f-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78e6f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78e6f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="78e6f-115">See also</span></span>
- [<span data-ttu-id="78e6f-116">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="78e6f-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
