---
title: Метод ICorRuntimeHost::LocksHeldByLogicalThread
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eed83cbc983d59e99b3a42e667e9e126316c263
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780094"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="6c044-102">Метод ICorRuntimeHost::LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="6c044-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="6c044-103">Возвращает число блокировок, которые текущий поток владеет.</span><span class="sxs-lookup"><span data-stu-id="6c044-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="6c044-104">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="6c044-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c044-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c044-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c044-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c044-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="6c044-107">[out] Указатель на число блокировок, которые текущий поток владеет.</span><span class="sxs-lookup"><span data-stu-id="6c044-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c044-108">Требования</span><span class="sxs-lookup"><span data-stu-id="6c044-108">Requirements</span></span>  
 <span data-ttu-id="6c044-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c044-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c044-110">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c044-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c044-111">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c044-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c044-112">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6c044-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c044-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6c044-113">See also</span></span>

- [<span data-ttu-id="6c044-114">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6c044-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
