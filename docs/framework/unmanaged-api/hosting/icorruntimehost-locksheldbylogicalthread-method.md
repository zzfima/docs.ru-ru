---
title: "Метод ICorRuntimeHost::LocksHeldByLogicalThread"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.LocksHeldByLogicalThread
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 82fa031e4842d81f7ddec3e7eeb64c9d7b02e566
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="16f56-102">Метод ICorRuntimeHost::LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="16f56-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="16f56-103">Возвращает число блокировок, которые текущий поток владеет.</span><span class="sxs-lookup"><span data-stu-id="16f56-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="16f56-104">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="16f56-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16f56-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16f56-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16f56-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="16f56-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="16f56-107">[out] Указатель на число блокировок, которые текущий поток владеет.</span><span class="sxs-lookup"><span data-stu-id="16f56-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16f56-108">Требования</span><span class="sxs-lookup"><span data-stu-id="16f56-108">Requirements</span></span>  
 <span data-ttu-id="16f56-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16f56-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16f56-110">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="16f56-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16f56-111">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="16f56-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16f56-112">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="16f56-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f56-113">См. также</span><span class="sxs-lookup"><span data-stu-id="16f56-113">See Also</span></span>  
 [<span data-ttu-id="16f56-114">ICorRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="16f56-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
