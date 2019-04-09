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
ms.openlocfilehash: d193f9aa4d051baa73944545d28a455495aeda40
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185774"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="f0c24-102">Метод ICorDebugCode::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f0c24-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="f0c24-103">Создает точку останова в этом сегменте кода, начиная с указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="f0c24-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0c24-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0c24-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0c24-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="f0c24-106">[in] Смещение, с которой будет создана точка останова.</span><span class="sxs-lookup"><span data-stu-id="f0c24-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="f0c24-107">[out] Указатель на адрес объекта «ICorDebugFunctionBreakpoint», который представляет точку останова.</span><span class="sxs-lookup"><span data-stu-id="f0c24-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0c24-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0c24-108">Remarks</span></span>  
 <span data-ttu-id="f0c24-109">Прежде чем точка останова не активна, его необходимо добавить в объект процесса.</span><span class="sxs-lookup"><span data-stu-id="f0c24-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="f0c24-110">Если этот код является код на промежуточном языке (MSIL), которая существует just-in-time (JIT)-компиляции, машинная версия кода, точка останова будет применяться в коде, а также JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="f0c24-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="f0c24-111">(То же самое значение true, если код является JIT-компиляции позже).</span><span class="sxs-lookup"><span data-stu-id="f0c24-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0c24-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f0c24-112">Requirements</span></span>  
 <span data-ttu-id="f0c24-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0c24-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0c24-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0c24-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0c24-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0c24-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f0c24-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f0c24-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0c24-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f0c24-117">See also</span></span>
