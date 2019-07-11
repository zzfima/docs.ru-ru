---
title: Метод ICorDebugChain::GetCaller
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d11693473dc4ed4438bbcad7f95c1b20adc1062b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744973"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="daafa-102">Метод ICorDebugChain::GetCaller</span><span class="sxs-lookup"><span data-stu-id="daafa-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="daafa-103">Получает цепочку, вызвавшей эту цепочку.</span><span class="sxs-lookup"><span data-stu-id="daafa-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daafa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="daafa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daafa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="daafa-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="daafa-106">[out] Указатель на адрес ICorDebugChain объект, представляющий цепочки вызовов.</span><span class="sxs-lookup"><span data-stu-id="daafa-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="daafa-107">Если эта цепочка была вызвана спонтанно (как можно добиться, если эта цепочка или отладчик инициализирован стека вызовов), `ppChain` будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="daafa-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daafa-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="daafa-108">Remarks</span></span>  
 <span data-ttu-id="daafa-109">Если вызов был маршалирован в потоки, цепочки вызовов возможно в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="daafa-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daafa-110">Требования</span><span class="sxs-lookup"><span data-stu-id="daafa-110">Requirements</span></span>  
 <span data-ttu-id="daafa-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daafa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daafa-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="daafa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="daafa-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daafa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daafa-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daafa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
