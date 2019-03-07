---
title: Метод ICorDebugAppDomain::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetProcess method [.NET Framework debugging]
ms.assetid: 9d0b9628-a91c-40d0-b9bc-00b34a396b8f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b05c35c810630897e4a7bd28e1cbe8cedefefb1f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489371"
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="da765-102">Метод ICorDebugAppDomain::GetProcess</span><span class="sxs-lookup"><span data-stu-id="da765-102">ICorDebugAppDomain::GetProcess Method</span></span>
<span data-ttu-id="da765-103">Получает процесс, содержащий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="da765-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da765-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da765-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da765-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="da765-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="da765-106">[out] Указатель на адрес объекта ICorDebugProcess, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="da765-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da765-107">Требования</span><span class="sxs-lookup"><span data-stu-id="da765-107">Requirements</span></span>  
 <span data-ttu-id="da765-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da765-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da765-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da765-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da765-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da765-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da765-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da765-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
