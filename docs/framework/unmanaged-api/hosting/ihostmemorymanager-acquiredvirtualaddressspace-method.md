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
ms.openlocfilehash: b70454cd1e2d6d38e6ca4d0ea0bd8974963c201c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136732"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="93955-102">Метод IHostMemoryManager::AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="93955-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="93955-103">Уведомляет узел о том, что среда CLR получила указанную память из операционной системы.</span><span class="sxs-lookup"><span data-stu-id="93955-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93955-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93955-104">Syntax</span></span>  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93955-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="93955-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="93955-106">окне Начальный адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="93955-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="93955-107">окне Размер памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="93955-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93955-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="93955-108">Remarks</span></span>  
 <span data-ttu-id="93955-109">Метод `AcquiredVirtualAddressSpace` является методом обратного вызова и должен быть реализован модулем записи размещающего приложения.</span><span class="sxs-lookup"><span data-stu-id="93955-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="93955-110">Он вызывается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="93955-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93955-111">Требования</span><span class="sxs-lookup"><span data-stu-id="93955-111">Requirements</span></span>  
 <span data-ttu-id="93955-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93955-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93955-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="93955-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93955-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="93955-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93955-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93955-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93955-116">См. также</span><span class="sxs-lookup"><span data-stu-id="93955-116">See also</span></span>

- [<span data-ttu-id="93955-117">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="93955-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
