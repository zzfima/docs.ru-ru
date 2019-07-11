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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e959ce7a77ad6ceb7f2fc848193cbd9fff028279
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739619"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="9f0ad-102">Перечисление CorDebugSetContextFlag</span><span class="sxs-lookup"><span data-stu-id="9f0ad-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="9f0ad-103">Указывает происхождение контекста: взят из активного (или листового) кадра в стеке или был вычислен в результате освобождения другого кадра.</span><span class="sxs-lookup"><span data-stu-id="9f0ad-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f0ad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f0ad-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="9f0ad-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9f0ad-105">Members</span></span>  
  
|<span data-ttu-id="9f0ad-106">Член</span><span class="sxs-lookup"><span data-stu-id="9f0ad-106">Member</span></span>|<span data-ttu-id="9f0ad-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9f0ad-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9f0ad-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="9f0ad-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="9f0ad-109">Контекст является активный контекст потока.</span><span class="sxs-lookup"><span data-stu-id="9f0ad-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="9f0ad-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="9f0ad-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="9f0ad-111">Контекст был вычислен в результате освобождения другого кадра.</span><span class="sxs-lookup"><span data-stu-id="9f0ad-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f0ad-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f0ad-112">Remarks</span></span>  
 <span data-ttu-id="9f0ad-113">`CorDebugSetContextFlag` Предоставляет значения, используемые [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="9f0ad-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f0ad-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9f0ad-114">Requirements</span></span>  
 <span data-ttu-id="9f0ad-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f0ad-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f0ad-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f0ad-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f0ad-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f0ad-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f0ad-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f0ad-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0ad-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9f0ad-119">See also</span></span>

- [<span data-ttu-id="9f0ad-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="9f0ad-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="9f0ad-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="9f0ad-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
