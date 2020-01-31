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
ms.openlocfilehash: a443332e4f2b0351e99754fae610af39268bb105
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789267"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="337b8-102">Перечисление CorDebugSetContextFlag</span><span class="sxs-lookup"><span data-stu-id="337b8-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="337b8-103">Указывает происхождение контекста: взят из активного (или листового) кадра в стеке или был вычислен в результате освобождения другого кадра.</span><span class="sxs-lookup"><span data-stu-id="337b8-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="337b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="337b8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="337b8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="337b8-105">Members</span></span>  
  
|<span data-ttu-id="337b8-106">Член</span><span class="sxs-lookup"><span data-stu-id="337b8-106">Member</span></span>|<span data-ttu-id="337b8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="337b8-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="337b8-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="337b8-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="337b8-109">Контекст является активным контекстом потока.</span><span class="sxs-lookup"><span data-stu-id="337b8-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="337b8-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="337b8-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="337b8-111">Контекст был вычислен путем очистки от другого кадра.</span><span class="sxs-lookup"><span data-stu-id="337b8-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="337b8-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="337b8-112">Remarks</span></span>  
 <span data-ttu-id="337b8-113">`CorDebugSetContextFlag` предоставляет значения, используемые методом [икордебугстакквалк:: SetContext](icordebugstackwalk-setcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="337b8-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="337b8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="337b8-114">Requirements</span></span>  
 <span data-ttu-id="337b8-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="337b8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="337b8-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="337b8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="337b8-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="337b8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="337b8-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337b8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337b8-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="337b8-119">See also</span></span>

- [<span data-ttu-id="337b8-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="337b8-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="337b8-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="337b8-121">Debugging</span></span>](index.md)
