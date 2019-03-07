---
title: Метод ICorDebugChain::GetThread
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ab2b584b4a3e9bef17110f3084dc93efb2e5167
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481655"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="bd334-102">Метод ICorDebugChain::GetThread</span><span class="sxs-lookup"><span data-stu-id="bd334-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="bd334-103">Получает часть физических обсуждение, на которое эта цепочка вызовов.</span><span class="sxs-lookup"><span data-stu-id="bd334-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd334-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd334-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd334-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd334-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="bd334-106">[out] Указатель на объект, представляющий физическом потоке ICorDebugThread этой цепочке вызовов является частью.</span><span class="sxs-lookup"><span data-stu-id="bd334-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd334-107">Требования</span><span class="sxs-lookup"><span data-stu-id="bd334-107">Requirements</span></span>  
 <span data-ttu-id="bd334-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd334-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd334-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd334-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd334-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd334-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd334-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd334-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
