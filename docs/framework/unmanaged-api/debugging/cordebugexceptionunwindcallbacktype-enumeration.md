---
title: Перечисление CorDebugExceptionUnwindCallbackType
ms.date: 03/30/2017
api_name:
- CorDebugExceptionUnwindCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionUnwindCallbackType
helpviewer_keywords:
- CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408e72eeaa1dac83c45488d186425f30c6043280
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786377"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="866d5-102">Перечисление CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="866d5-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="866d5-103">Указывает событие, о котором сообщает обратный вызов во время фазы перемотки.</span><span class="sxs-lookup"><span data-stu-id="866d5-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="866d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="866d5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="866d5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="866d5-105">Members</span></span>  
  
|<span data-ttu-id="866d5-106">Член</span><span class="sxs-lookup"><span data-stu-id="866d5-106">Member</span></span>|<span data-ttu-id="866d5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="866d5-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="866d5-108">Начало процесса очистки.</span><span class="sxs-lookup"><span data-stu-id="866d5-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="866d5-109">Было перехвачено исключение.</span><span class="sxs-lookup"><span data-stu-id="866d5-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="866d5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="866d5-110">Requirements</span></span>  
 <span data-ttu-id="866d5-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="866d5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="866d5-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="866d5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="866d5-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="866d5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="866d5-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="866d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="866d5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="866d5-115">See also</span></span>

- [<span data-ttu-id="866d5-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="866d5-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
