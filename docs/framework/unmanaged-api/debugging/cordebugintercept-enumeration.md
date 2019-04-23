---
title: Перечисление CorDebugIntercept
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0791a59e0325668960dcfc98816920db55bcfb87
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199938"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="7910d-102">Перечисление CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="7910d-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="7910d-103">Указывает типы кода, которые могут быть перехвачены (то есть типы, для которых возможно пошаговое выполнение).</span><span class="sxs-lookup"><span data-stu-id="7910d-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7910d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7910d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="7910d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7910d-105">Members</span></span>  
  
|<span data-ttu-id="7910d-106">Член</span><span class="sxs-lookup"><span data-stu-id="7910d-106">Member</span></span>|<span data-ttu-id="7910d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7910d-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="7910d-108">Перехват кода невозможен.</span><span class="sxs-lookup"><span data-stu-id="7910d-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="7910d-109">Допускается перехват конструктора.</span><span class="sxs-lookup"><span data-stu-id="7910d-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="7910d-110">Допускается перехват исключения.</span><span class="sxs-lookup"><span data-stu-id="7910d-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="7910d-111">Допускается перехват кода, который принудительно включает систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="7910d-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="7910d-112">Допускается перехват политики контекста.</span><span class="sxs-lookup"><span data-stu-id="7910d-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="7910d-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="7910d-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="7910d-114">Возможен перехват любого кода.</span><span class="sxs-lookup"><span data-stu-id="7910d-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7910d-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="7910d-115">Remarks</span></span>  
 <span data-ttu-id="7910d-116">Используйте [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) метод, чтобы установить те типы кода, которые могут быть перехвачены.</span><span class="sxs-lookup"><span data-stu-id="7910d-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7910d-117">Требования</span><span class="sxs-lookup"><span data-stu-id="7910d-117">Requirements</span></span>  
 <span data-ttu-id="7910d-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7910d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7910d-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7910d-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7910d-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7910d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7910d-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7910d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7910d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7910d-122">See also</span></span>

- [<span data-ttu-id="7910d-123">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="7910d-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
