---
title: Метод ICorDebugChain::GetCallee
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79743b78ea3d19bab4756b580d2feddd07e0a23b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744982"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="03860-102">Метод ICorDebugChain::GetCallee</span><span class="sxs-lookup"><span data-stu-id="03860-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="03860-103">Получает цепочку, вызванная этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="03860-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03860-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03860-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03860-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="03860-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="03860-106">[out] Указатель на адрес ICorDebugChain объект, представляющий вызываемый цепочки.</span><span class="sxs-lookup"><span data-stu-id="03860-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="03860-107">Если эта цепочка выполняемый в текущий момент (то есть, если эта цепочка не находится в состоянии для вызываемой цепочки для возврата), `ppChain` будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="03860-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03860-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="03860-108">Remarks</span></span>  
 <span data-ttu-id="03860-109">Эта цепочка будет ожидать, чтобы вернуть свое выполнение вызванной цепочка.</span><span class="sxs-lookup"><span data-stu-id="03860-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="03860-110">Вызванная цепь может находиться в другом потоке, в случае маршалированного вызовы между потоками.</span><span class="sxs-lookup"><span data-stu-id="03860-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03860-111">Требования</span><span class="sxs-lookup"><span data-stu-id="03860-111">Requirements</span></span>  
 <span data-ttu-id="03860-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03860-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03860-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03860-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03860-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03860-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03860-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03860-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
