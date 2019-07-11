---
title: Метод ICorDebugChain::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a6db1990df2ed6b29d548c147ed40b5bc98254d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745689"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="7579f-102">Метод ICorDebugChain::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="7579f-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="7579f-103">Получает диапазон адресов сегмента стека для этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="7579f-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7579f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7579f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7579f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7579f-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="7579f-106">[out] Указатель на `CORDB_ADDRESS` значение, равное начальный адрес сегмента стека.</span><span class="sxs-lookup"><span data-stu-id="7579f-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="7579f-107">[out] Указатель на `CORDB_ADDRESS` значение, равное конечный адрес сегмента стека.</span><span class="sxs-lookup"><span data-stu-id="7579f-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7579f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="7579f-108">Remarks</span></span>  
 <span data-ttu-id="7579f-109">Числовой диапазон имеет смысл только для сравнения расположений кадра стека.</span><span class="sxs-lookup"><span data-stu-id="7579f-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="7579f-110">Нельзя делать никаких предположений о фактическое содержимое в стеке.</span><span class="sxs-lookup"><span data-stu-id="7579f-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7579f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7579f-111">Requirements</span></span>  
 <span data-ttu-id="7579f-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7579f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7579f-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7579f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7579f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7579f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7579f-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7579f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
