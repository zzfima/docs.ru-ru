---
title: Метод IHostMemoryManager::AcquiredVirtualAddressSpace
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6133b558e62d66cfaac201317f66d784aac264c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513715"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="e9aed-102">Метод IHostMemoryManager::AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="e9aed-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="e9aed-103">Уведомляет основное приложение, что общеязыковая среда выполнения (CLR) получила указанную память от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="e9aed-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9aed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9aed-104">Syntax</span></span>  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9aed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9aed-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="e9aed-106">[in] Начальный адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="e9aed-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="e9aed-107">[in] Размер в байтах объем памяти.</span><span class="sxs-lookup"><span data-stu-id="e9aed-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9aed-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9aed-108">Remarks</span></span>  
 <span data-ttu-id="e9aed-109">`AcquiredVirtualAddressSpace` Метод является методом обратного вызова и должны быть реализованы модулем записи ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="e9aed-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="e9aed-110">Он вызывается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="e9aed-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9aed-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e9aed-111">Requirements</span></span>  
 <span data-ttu-id="e9aed-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9aed-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9aed-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9aed-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9aed-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9aed-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9aed-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9aed-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9aed-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e9aed-116">See also</span></span>
- [<span data-ttu-id="e9aed-117">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="e9aed-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
