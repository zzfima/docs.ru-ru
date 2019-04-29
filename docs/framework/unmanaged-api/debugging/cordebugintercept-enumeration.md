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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651705"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="c7e7b-102">Перечисление CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="c7e7b-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="c7e7b-103">Указывает типы кода, которые могут быть перехвачены (то есть типы, для которых возможно пошаговое выполнение).</span><span class="sxs-lookup"><span data-stu-id="c7e7b-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7e7b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7e7b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c7e7b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c7e7b-105">Members</span></span>  
  
|<span data-ttu-id="c7e7b-106">Член</span><span class="sxs-lookup"><span data-stu-id="c7e7b-106">Member</span></span>|<span data-ttu-id="c7e7b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c7e7b-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="c7e7b-108">Перехват кода невозможен.</span><span class="sxs-lookup"><span data-stu-id="c7e7b-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="c7e7b-109">Допускается перехват конструктора.</span><span class="sxs-lookup"><span data-stu-id="c7e7b-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="c7e7b-110">Допускается перехват исключения.</span><span class="sxs-lookup"><span data-stu-id="c7e7b-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="c7e7b-111">Допускается перехват кода, который принудительно включает систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="c7e7b-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="c7e7b-112">Допускается перехват политики контекста.</span><span class="sxs-lookup"><span data-stu-id="c7e7b-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="c7e7b-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="c7e7b-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="c7e7b-114">Возможен перехват любого кода.</span><span class="sxs-lookup"><span data-stu-id="c7e7b-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7e7b-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7e7b-115">Remarks</span></span>  
 <span data-ttu-id="c7e7b-116">Используйте [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) метод, чтобы установить те типы кода, которые могут быть перехвачены.</span><span class="sxs-lookup"><span data-stu-id="c7e7b-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7e7b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="c7e7b-117">Requirements</span></span>  
 <span data-ttu-id="c7e7b-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7e7b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7e7b-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7e7b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7e7b-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7e7b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7e7b-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7e7b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e7b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c7e7b-122">See also</span></span>

- [<span data-ttu-id="c7e7b-123">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="c7e7b-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
