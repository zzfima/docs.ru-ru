---
title: Метод ICorDebugFrame::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9f58e66286f5e3e169507efd2f87ce10e9d323b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754855"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="010b9-102">Метод ICorDebugFrame::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="010b9-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="010b9-103">Возвращает диапазон абсолютных адресов этого кадра стека.</span><span class="sxs-lookup"><span data-stu-id="010b9-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="010b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="010b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="010b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="010b9-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="010b9-106">[out] Указатель на `CORDB_ADDRESS` , указывающий начальный адрес кадра стека, представленный этим `ICorDebugFrame` объекта.</span><span class="sxs-lookup"><span data-stu-id="010b9-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="010b9-107">[out] Указатель на `CORDB_ADDRESS` , указывающий конечный адрес кадра стека, представленный этим `ICorDebugFrame` объекта.</span><span class="sxs-lookup"><span data-stu-id="010b9-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="010b9-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="010b9-108">Remarks</span></span>  
 <span data-ttu-id="010b9-109">Диапазон адресов стека полезно для соединения вместе перемежаемых трассировок стека из нескольких обработчиков отладки.</span><span class="sxs-lookup"><span data-stu-id="010b9-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="010b9-110">Числовой диапазон не предоставляет сведений о содержимом кадра стека.</span><span class="sxs-lookup"><span data-stu-id="010b9-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="010b9-111">Он имеет смысл только для сравнения расположений кадра стека.</span><span class="sxs-lookup"><span data-stu-id="010b9-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="010b9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="010b9-112">Requirements</span></span>  
 <span data-ttu-id="010b9-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="010b9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="010b9-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="010b9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="010b9-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="010b9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="010b9-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="010b9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
