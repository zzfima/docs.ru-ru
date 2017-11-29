---
title: "Метод IHostMemoryManager::NeedsVirtualAddressSpace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.NeedsVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62ceb9e5b4d5843b8e2adad344b3ffb662ab3aff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="1b37a-102">Метод IHostMemoryManager::NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="1b37a-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="1b37a-103">Уведомляет основное приложение, общеязыковой среды выполнения (CLR) будет пытаться использовать указанный объем памяти.</span><span class="sxs-lookup"><span data-stu-id="1b37a-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b37a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b37a-104">Syntax</span></span>  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b37a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b37a-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="1b37a-106">[in] Начальный адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="1b37a-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="1b37a-107">[in] Размер в байтах в памяти.</span><span class="sxs-lookup"><span data-stu-id="1b37a-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b37a-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b37a-108">Remarks</span></span>  
 <span data-ttu-id="1b37a-109">`NeedsVirtualAddressSpace` Метод является методом обратного вызова и должны быть реализованы разработчиком ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="1b37a-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="1b37a-110">Он вызывается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="1b37a-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="1b37a-111">Если узел не требуется среда CLR для использования указанного объема памяти, может вернуть значение E_OUTOFMEMORY HRESULT.</span><span class="sxs-lookup"><span data-stu-id="1b37a-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b37a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1b37a-112">Requirements</span></span>  
 <span data-ttu-id="1b37a-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b37a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b37a-114">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1b37a-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b37a-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b37a-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b37a-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b37a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b37a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1b37a-117">See Also</span></span>  
 [<span data-ttu-id="1b37a-118">IHostMemoryManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1b37a-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
