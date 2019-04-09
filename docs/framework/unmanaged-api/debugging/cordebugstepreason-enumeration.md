---
title: Перечисление CorDebugStepReason
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ce2b23306e7e38f3982f8d5a4b377aa2f9547c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186255"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="a15a8-102">Перечисление CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="a15a8-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="a15a8-103">Указывает результат отдельного шага.</span><span class="sxs-lookup"><span data-stu-id="a15a8-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a15a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a15a8-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a><span data-ttu-id="a15a8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="a15a8-105">Members</span></span>  
  
|<span data-ttu-id="a15a8-106">Член</span><span class="sxs-lookup"><span data-stu-id="a15a8-106">Member</span></span>|<span data-ttu-id="a15a8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a15a8-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="a15a8-108">Пошаговое выполнение завершено нормально в ту же функцию.</span><span class="sxs-lookup"><span data-stu-id="a15a8-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="a15a8-109">Шаг с заходом продолжена нормально после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="a15a8-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="a15a8-110">Шаг с заходом продолжена нормально в начале вновь вызванной функции.</span><span class="sxs-lookup"><span data-stu-id="a15a8-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="a15a8-111">Возникло исключение и передан элемент управления фильтра исключений.</span><span class="sxs-lookup"><span data-stu-id="a15a8-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="a15a8-112">Возникло исключение, и элемент управления был передан в обработчик исключений.</span><span class="sxs-lookup"><span data-stu-id="a15a8-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="a15a8-113">Управление было передано перехватчику.</span><span class="sxs-lookup"><span data-stu-id="a15a8-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="a15a8-114">Выход потока до выполнения шага.</span><span class="sxs-lookup"><span data-stu-id="a15a8-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a15a8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a15a8-115">Requirements</span></span>  
 <span data-ttu-id="a15a8-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a15a8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a15a8-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a15a8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a15a8-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a15a8-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a15a8-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a15a8-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a15a8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a15a8-120">See also</span></span>

- [<span data-ttu-id="a15a8-121">Метод StepComplete</span><span class="sxs-lookup"><span data-stu-id="a15a8-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="a15a8-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="a15a8-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
