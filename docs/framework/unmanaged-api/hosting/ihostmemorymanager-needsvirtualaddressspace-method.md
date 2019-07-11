---
title: Метод IHostMemoryManager::NeedsVirtualAddressSpace
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57ed64ad8a6ae8ef46f423471436c3fce29d6fe5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767818"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="ec91b-102">Метод IHostMemoryManager::NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="ec91b-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="ec91b-103">Уведомляет основное приложение, что общеязыковая среда выполнения (CLR) будет пытаться использовать указанный объем памяти.</span><span class="sxs-lookup"><span data-stu-id="ec91b-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec91b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec91b-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec91b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec91b-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="ec91b-106">[in] Начальный адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="ec91b-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="ec91b-107">[in] Размер в байтах объем памяти.</span><span class="sxs-lookup"><span data-stu-id="ec91b-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec91b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec91b-108">Remarks</span></span>  
 <span data-ttu-id="ec91b-109">`NeedsVirtualAddressSpace` Метод является методом обратного вызова и должны быть реализованы модулем записи ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="ec91b-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="ec91b-110">Он вызывается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="ec91b-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="ec91b-111">Если узел не должна выполнять среда CLR для использования указанного объема памяти, может вернуть значение E_OUTOFMEMORY HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ec91b-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec91b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ec91b-112">Requirements</span></span>  
 <span data-ttu-id="ec91b-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec91b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec91b-114">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ec91b-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec91b-115">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec91b-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec91b-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec91b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec91b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ec91b-117">See also</span></span>

- [<span data-ttu-id="ec91b-118">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="ec91b-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
