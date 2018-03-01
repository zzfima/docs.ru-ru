---
title: "Метод IHostMemoryManager::NeedsVirtualAddressSpace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9251cbadaf182cda8d52f3f5792452310561c376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="5d6ac-102">Метод IHostMemoryManager::NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="5d6ac-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="5d6ac-103">Уведомляет основное приложение, общеязыковой среды выполнения (CLR) будет пытаться использовать указанный объем памяти.</span><span class="sxs-lookup"><span data-stu-id="5d6ac-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d6ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d6ac-104">Syntax</span></span>  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d6ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d6ac-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="5d6ac-106">[in] Начальный адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="5d6ac-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="5d6ac-107">[in] Размер в байтах в памяти.</span><span class="sxs-lookup"><span data-stu-id="5d6ac-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d6ac-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d6ac-108">Remarks</span></span>  
 <span data-ttu-id="5d6ac-109">`NeedsVirtualAddressSpace` Метод является методом обратного вызова и должны быть реализованы разработчиком ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="5d6ac-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="5d6ac-110">Он вызывается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="5d6ac-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="5d6ac-111">Если узел не требуется среда CLR для использования указанного объема памяти, может вернуть значение E_OUTOFMEMORY HRESULT.</span><span class="sxs-lookup"><span data-stu-id="5d6ac-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d6ac-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5d6ac-112">Requirements</span></span>  
 <span data-ttu-id="5d6ac-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d6ac-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d6ac-114">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d6ac-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d6ac-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d6ac-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d6ac-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d6ac-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6ac-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5d6ac-117">See Also</span></span>  
 [<span data-ttu-id="5d6ac-118">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="5d6ac-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
