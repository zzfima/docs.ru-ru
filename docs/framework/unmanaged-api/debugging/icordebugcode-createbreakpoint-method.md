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
ms.openlocfilehash: df27d2ab609551bb7a7f6f4b0ff8c7118c9f93f8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478680"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="ce3ec-102">Метод ICorDebugCode::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ce3ec-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="ce3ec-103">Создает точку останова в этом сегменте кода, начиная с указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="ce3ec-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce3ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce3ec-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce3ec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce3ec-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="ce3ec-106">[in] Смещение, с которой будет создана точка останова.</span><span class="sxs-lookup"><span data-stu-id="ce3ec-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="ce3ec-107">[out] Указатель на адрес объекта «ICorDebugFunctionBreakpoint», который представляет точку останова.</span><span class="sxs-lookup"><span data-stu-id="ce3ec-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce3ec-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="ce3ec-108">Remarks</span></span>  
 <span data-ttu-id="ce3ec-109">Прежде чем точка останова не активна, его необходимо добавить в объект процесса.</span><span class="sxs-lookup"><span data-stu-id="ce3ec-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="ce3ec-110">Если этот код является код на промежуточном языке (MSIL), которая существует just-in-time (JIT)-компиляции, машинная версия кода, точка останова будет применяться в коде, а также JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="ce3ec-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="ce3ec-111">(То же самое значение true, если код является JIT-компиляции позже).</span><span class="sxs-lookup"><span data-stu-id="ce3ec-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce3ec-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ce3ec-112">Requirements</span></span>  
 <span data-ttu-id="ce3ec-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce3ec-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce3ec-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce3ec-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce3ec-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce3ec-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce3ec-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce3ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce3ec-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ce3ec-117">See also</span></span>

