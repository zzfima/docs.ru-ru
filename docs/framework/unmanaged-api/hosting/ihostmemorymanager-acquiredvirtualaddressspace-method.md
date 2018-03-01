---
title: "Метод IHostMemoryManager::AcquiredVirtualAddressSpace"
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
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: af80a43b86b1a16c5afe2741cb3d2bd7f0d874ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="33e01-102">Метод IHostMemoryManager::AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="33e01-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="33e01-103">Уведомляет узел, что общеязыковой среды выполнения (CLR) получила указанную память от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="33e01-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33e01-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33e01-104">Syntax</span></span>  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33e01-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="33e01-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="33e01-106">[in] Начальный адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="33e01-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="33e01-107">[in] Размер в байтах в памяти.</span><span class="sxs-lookup"><span data-stu-id="33e01-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33e01-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="33e01-108">Remarks</span></span>  
 <span data-ttu-id="33e01-109">`AcquiredVirtualAddressSpace` Метод является методом обратного вызова и должны быть реализованы разработчиком ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="33e01-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="33e01-110">Он вызывается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="33e01-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33e01-111">Требования</span><span class="sxs-lookup"><span data-stu-id="33e01-111">Requirements</span></span>  
 <span data-ttu-id="33e01-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33e01-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33e01-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33e01-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33e01-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33e01-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33e01-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33e01-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e01-116">См. также</span><span class="sxs-lookup"><span data-stu-id="33e01-116">See Also</span></span>  
 [<span data-ttu-id="33e01-117">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="33e01-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
