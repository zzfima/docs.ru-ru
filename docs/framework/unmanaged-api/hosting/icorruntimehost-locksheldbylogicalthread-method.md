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
ms.openlocfilehash: 90af015de4428f75330de89978a7fc0a4b26750b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144200"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="e9c3b-102">Метод ICorRuntimeHost::LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="e9c3b-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="e9c3b-103">Возвращает число блокировок, которые текущий поток владеет.</span><span class="sxs-lookup"><span data-stu-id="e9c3b-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="e9c3b-104">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="e9c3b-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c3b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9c3b-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9c3b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9c3b-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="e9c3b-107">[out] Указатель на число блокировок, которые текущий поток владеет.</span><span class="sxs-lookup"><span data-stu-id="e9c3b-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9c3b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="e9c3b-108">Requirements</span></span>  
 <span data-ttu-id="e9c3b-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9c3b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9c3b-110">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9c3b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9c3b-111">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9c3b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9c3b-112">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="e9c3b-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c3b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e9c3b-113">See also</span></span>

- [<span data-ttu-id="e9c3b-114">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e9c3b-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
