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
ms.openlocfilehash: 8ce48b63a92e84ce92da0dcf35a6242744c1a8c3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778415"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="74c8d-102">Перечисление CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="74c8d-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="74c8d-103">Указывает типы кода, которые могут быть перехвачены (то есть типы, для которых возможно пошаговое выполнение).</span><span class="sxs-lookup"><span data-stu-id="74c8d-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74c8d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74c8d-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="74c8d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="74c8d-105">Members</span></span>  
  
|<span data-ttu-id="74c8d-106">Член</span><span class="sxs-lookup"><span data-stu-id="74c8d-106">Member</span></span>|<span data-ttu-id="74c8d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="74c8d-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="74c8d-108">Перехват кода невозможен.</span><span class="sxs-lookup"><span data-stu-id="74c8d-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="74c8d-109">Допускается перехват конструктора.</span><span class="sxs-lookup"><span data-stu-id="74c8d-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="74c8d-110">Допускается перехват исключения.</span><span class="sxs-lookup"><span data-stu-id="74c8d-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="74c8d-111">Допускается перехват кода, который принудительно включает систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="74c8d-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="74c8d-112">Допускается перехват политики контекста.</span><span class="sxs-lookup"><span data-stu-id="74c8d-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="74c8d-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="74c8d-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="74c8d-114">Возможен перехват любого кода.</span><span class="sxs-lookup"><span data-stu-id="74c8d-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74c8d-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="74c8d-115">Remarks</span></span>  
 <span data-ttu-id="74c8d-116">Используйте метод [ICorDebugStepper:: сетинтерцептмаск](icordebugstepper-setinterceptmask-method.md) , чтобы установить типы кода, которые могут быть перехвачены.</span><span class="sxs-lookup"><span data-stu-id="74c8d-116">Use the [ICorDebugStepper::SetInterceptMask](icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74c8d-117">Требования</span><span class="sxs-lookup"><span data-stu-id="74c8d-117">Requirements</span></span>  
 <span data-ttu-id="74c8d-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74c8d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74c8d-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74c8d-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74c8d-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74c8d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74c8d-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74c8d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c8d-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="74c8d-122">See also</span></span>

- [<span data-ttu-id="74c8d-123">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="74c8d-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
