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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723164"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="70d85-102">Перечисление CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="70d85-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="70d85-103">Указывает результат отдельного шага.</span><span class="sxs-lookup"><span data-stu-id="70d85-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70d85-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="70d85-105">Участники</span><span class="sxs-lookup"><span data-stu-id="70d85-105">Members</span></span>  
  
|<span data-ttu-id="70d85-106">Член</span><span class="sxs-lookup"><span data-stu-id="70d85-106">Member</span></span>|<span data-ttu-id="70d85-107">Описание</span><span class="sxs-lookup"><span data-stu-id="70d85-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="70d85-108">Пошаговое выполнение завершено нормально в ту же функцию.</span><span class="sxs-lookup"><span data-stu-id="70d85-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="70d85-109">Шаг с заходом продолжена нормально после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="70d85-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="70d85-110">Шаг с заходом продолжена нормально в начале вновь вызванной функции.</span><span class="sxs-lookup"><span data-stu-id="70d85-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="70d85-111">Возникло исключение и передан элемент управления фильтра исключений.</span><span class="sxs-lookup"><span data-stu-id="70d85-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="70d85-112">Возникло исключение, и элемент управления был передан в обработчик исключений.</span><span class="sxs-lookup"><span data-stu-id="70d85-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="70d85-113">Управление было передано перехватчику.</span><span class="sxs-lookup"><span data-stu-id="70d85-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="70d85-114">Выход потока до выполнения шага.</span><span class="sxs-lookup"><span data-stu-id="70d85-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70d85-115">Требования</span><span class="sxs-lookup"><span data-stu-id="70d85-115">Requirements</span></span>  
 <span data-ttu-id="70d85-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70d85-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70d85-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70d85-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70d85-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70d85-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70d85-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70d85-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d85-120">См. также</span><span class="sxs-lookup"><span data-stu-id="70d85-120">See also</span></span>

- [<span data-ttu-id="70d85-121">Метод StepComplete</span><span class="sxs-lookup"><span data-stu-id="70d85-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="70d85-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="70d85-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
