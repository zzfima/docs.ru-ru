---
title: "Перечисление CorDebugStepReason"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 68c4f9452f8ccc9b4d48ee67755a311f32540247
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="45f25-102">Перечисление CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="45f25-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="45f25-103">Указывает результат отдельного шага.</span><span class="sxs-lookup"><span data-stu-id="45f25-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45f25-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45f25-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="45f25-105">Участники</span><span class="sxs-lookup"><span data-stu-id="45f25-105">Members</span></span>  
  
|<span data-ttu-id="45f25-106">Член</span><span class="sxs-lookup"><span data-stu-id="45f25-106">Member</span></span>|<span data-ttu-id="45f25-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="45f25-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="45f25-108">Пошаговое выполнение завершено нормально в той же функции.</span><span class="sxs-lookup"><span data-stu-id="45f25-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="45f25-109">Шаг с заходом продолжена нормально после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="45f25-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="45f25-110">Шаг с заходом продолжена нормально в начале вновь вызванной функции.</span><span class="sxs-lookup"><span data-stu-id="45f25-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="45f25-111">Возникло исключение и управление было передано фильтра исключений.</span><span class="sxs-lookup"><span data-stu-id="45f25-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="45f25-112">Возникло исключение и управление было передано обработчику исключений.</span><span class="sxs-lookup"><span data-stu-id="45f25-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="45f25-113">Элемент управления был передан перехватчик.</span><span class="sxs-lookup"><span data-stu-id="45f25-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="45f25-114">Выход потока до выполнения шага.</span><span class="sxs-lookup"><span data-stu-id="45f25-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45f25-115">Требования</span><span class="sxs-lookup"><span data-stu-id="45f25-115">Requirements</span></span>  
 <span data-ttu-id="45f25-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45f25-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45f25-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45f25-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45f25-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45f25-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45f25-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45f25-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f25-120">См. также</span><span class="sxs-lookup"><span data-stu-id="45f25-120">See Also</span></span>  
 [<span data-ttu-id="45f25-121">Метод StepComplete</span><span class="sxs-lookup"><span data-stu-id="45f25-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)  
 [<span data-ttu-id="45f25-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="45f25-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
