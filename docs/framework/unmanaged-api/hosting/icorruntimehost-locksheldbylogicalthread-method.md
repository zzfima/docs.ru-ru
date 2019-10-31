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
ms.openlocfilehash: f6ef7e06d94cb22d266949927cb15105b1602d3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139529"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="cc165-102">Метод ICorRuntimeHost::LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="cc165-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="cc165-103">Возвращает число блокировок, удерживаемых текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="cc165-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="cc165-104">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="cc165-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc165-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc165-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc165-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc165-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="cc165-107">заполняет Указатель на число блокировок, удерживаемых текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="cc165-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc165-108">Требования</span><span class="sxs-lookup"><span data-stu-id="cc165-108">Requirements</span></span>  
 <span data-ttu-id="cc165-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc165-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc165-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cc165-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc165-111">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cc165-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc165-112">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="cc165-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc165-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cc165-113">See also</span></span>

- [<span data-ttu-id="cc165-114">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="cc165-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
