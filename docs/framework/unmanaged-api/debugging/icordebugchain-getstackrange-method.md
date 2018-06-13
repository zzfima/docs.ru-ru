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
ms.openlocfilehash: 226f8c431b90d53366aa5e504101e7de581ec570
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402474"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="35121-102">Метод ICorDebugChain::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="35121-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="35121-103">Возвращает диапазон адресов сегмента стека для этой цепи.</span><span class="sxs-lookup"><span data-stu-id="35121-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35121-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35121-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35121-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="35121-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="35121-106">[out] Указатель на `CORDB_ADDRESS` значение, которое начальный адрес сегмента стека.</span><span class="sxs-lookup"><span data-stu-id="35121-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="35121-107">[out] Указатель на `CORDB_ADDRESS` значение, которое конечный адрес сегмента стека.</span><span class="sxs-lookup"><span data-stu-id="35121-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35121-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="35121-108">Remarks</span></span>  
 <span data-ttu-id="35121-109">Числовой диапазон имеет смысл только для сравнения расположений кадров стека.</span><span class="sxs-lookup"><span data-stu-id="35121-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="35121-110">Нельзя делать никаких предположений о том, что фактически хранятся в стеке.</span><span class="sxs-lookup"><span data-stu-id="35121-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35121-111">Требования</span><span class="sxs-lookup"><span data-stu-id="35121-111">Requirements</span></span>  
 <span data-ttu-id="35121-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35121-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35121-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35121-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35121-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35121-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35121-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35121-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
