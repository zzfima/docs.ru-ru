---
title: Метод ICorDebugCode::CreateBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07f8be1a1831bc00eea3cfb659b46b67b6a78711
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747732"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="d8057-102">Метод ICorDebugCode::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d8057-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="d8057-103">Создает точку останова в этом сегменте кода, начиная с указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="d8057-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8057-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8057-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8057-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8057-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="d8057-106">[in] Смещение, с которой будет создана точка останова.</span><span class="sxs-lookup"><span data-stu-id="d8057-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="d8057-107">[out] Указатель на адрес объекта «ICorDebugFunctionBreakpoint», который представляет точку останова.</span><span class="sxs-lookup"><span data-stu-id="d8057-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8057-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d8057-108">Remarks</span></span>  
 <span data-ttu-id="d8057-109">Прежде чем точка останова не активна, его необходимо добавить в объект процесса.</span><span class="sxs-lookup"><span data-stu-id="d8057-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="d8057-110">Если этот код является код на промежуточном языке (MSIL), которая существует just-in-time (JIT)-компиляции, машинная версия кода, точка останова будет применяться в коде, а также JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="d8057-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="d8057-111">(То же самое значение true, если код является JIT-компиляции позже).</span><span class="sxs-lookup"><span data-stu-id="d8057-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8057-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d8057-112">Requirements</span></span>  
 <span data-ttu-id="d8057-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8057-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8057-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8057-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8057-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8057-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8057-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8057-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8057-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d8057-117">See also</span></span>
