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
ms.openlocfilehash: 64e697323377d664b7b1e36bbf5931a44465cc51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178955"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="408b8-102">Метод ICorDebugChain::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="408b8-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="408b8-103">Получает адресный диапазон сегмента стека для этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="408b8-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="408b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="408b8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="408b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="408b8-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="408b8-106">(ваут) Указатель на `CORDB_ADDRESS` значение, которое является исходным адресом сегмента стека.</span><span class="sxs-lookup"><span data-stu-id="408b8-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="408b8-107">(ваут) Указатель на `CORDB_ADDRESS` значение, которое является конечной адрес сегмента стека.</span><span class="sxs-lookup"><span data-stu-id="408b8-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="408b8-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="408b8-108">Remarks</span></span>  
 <span data-ttu-id="408b8-109">Числовой диапазон имеет смысл только для сравнения расположения стек-кадра.</span><span class="sxs-lookup"><span data-stu-id="408b8-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="408b8-110">Вы не можете делать какие-либо предположения о том, что на самом деле хранится в стеке.</span><span class="sxs-lookup"><span data-stu-id="408b8-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="408b8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="408b8-111">Requirements</span></span>  
 <span data-ttu-id="408b8-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="408b8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="408b8-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="408b8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="408b8-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="408b8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="408b8-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="408b8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
