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
ms.openlocfilehash: 8f6a3d425d4c2ae2146723a6acfc5ab9893f0fe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="f0937-102">Метод IHostMemoryManager::ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="f0937-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="f0937-103">Уведомляет узел об окончании общеязыковой среды выполнения (CLR) с помощью указанной памяти.</span><span class="sxs-lookup"><span data-stu-id="f0937-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0937-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0937-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0937-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0937-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="f0937-106">[in] Указатель на начальный адрес память освобождается.</span><span class="sxs-lookup"><span data-stu-id="f0937-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0937-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0937-107">Remarks</span></span>  
 <span data-ttu-id="f0937-108">`ReleasedVirtualAddressSpace` Метод является методом обратного вызова и должны быть реализованы разработчиком ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="f0937-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="f0937-109">Он вызывается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="f0937-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0937-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f0937-110">Requirements</span></span>  
 <span data-ttu-id="f0937-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0937-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0937-112">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f0937-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0937-113">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f0937-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0937-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0937-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0937-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f0937-115">See Also</span></span>  
 [<span data-ttu-id="f0937-116">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="f0937-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
