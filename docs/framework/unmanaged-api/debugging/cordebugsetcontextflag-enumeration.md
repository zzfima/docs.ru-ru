---
title: Перечисление CorDebugSetContextFlag
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
ms.openlocfilehash: 251c96042e8e56112015fb869176c708322267f6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097268"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="337a1-102">Перечисление CorDebugSetContextFlag</span><span class="sxs-lookup"><span data-stu-id="337a1-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="337a1-103">Указывает происхождение контекста: взят из активного (или листового) кадра в стеке или был вычислен в результате освобождения другого кадра.</span><span class="sxs-lookup"><span data-stu-id="337a1-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="337a1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="337a1-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="337a1-105">Члены</span><span class="sxs-lookup"><span data-stu-id="337a1-105">Members</span></span>  
  
|<span data-ttu-id="337a1-106">Член</span><span class="sxs-lookup"><span data-stu-id="337a1-106">Member</span></span>|<span data-ttu-id="337a1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="337a1-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="337a1-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="337a1-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="337a1-109">Контекст является активным контекстом потока.</span><span class="sxs-lookup"><span data-stu-id="337a1-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="337a1-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="337a1-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="337a1-111">Контекст был вычислен путем очистки от другого кадра.</span><span class="sxs-lookup"><span data-stu-id="337a1-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="337a1-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="337a1-112">Remarks</span></span>  
 <span data-ttu-id="337a1-113">`CorDebugSetContextFlag` предоставляет значения, используемые методом [икордебугстакквалк:: SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="337a1-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="337a1-114">Требования</span><span class="sxs-lookup"><span data-stu-id="337a1-114">Requirements</span></span>  
 <span data-ttu-id="337a1-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="337a1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="337a1-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="337a1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="337a1-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="337a1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="337a1-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337a1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337a1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="337a1-119">See also</span></span>

- [<span data-ttu-id="337a1-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="337a1-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="337a1-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="337a1-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
