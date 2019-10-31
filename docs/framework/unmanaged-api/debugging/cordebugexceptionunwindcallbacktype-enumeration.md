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
ms.openlocfilehash: 5004cd293b64436c41caef1c7393d2229d1a6ccf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098482"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="dcf60-102">Перечисление CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="dcf60-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="dcf60-103">Указывает событие, о котором сообщает обратный вызов во время фазы перемотки.</span><span class="sxs-lookup"><span data-stu-id="dcf60-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf60-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcf60-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="dcf60-105">Члены</span><span class="sxs-lookup"><span data-stu-id="dcf60-105">Members</span></span>  
  
|<span data-ttu-id="dcf60-106">Член</span><span class="sxs-lookup"><span data-stu-id="dcf60-106">Member</span></span>|<span data-ttu-id="dcf60-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dcf60-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="dcf60-108">Начало процесса очистки.</span><span class="sxs-lookup"><span data-stu-id="dcf60-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="dcf60-109">Исключение перехвачено.</span><span class="sxs-lookup"><span data-stu-id="dcf60-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dcf60-110">Требования</span><span class="sxs-lookup"><span data-stu-id="dcf60-110">Requirements</span></span>  
 <span data-ttu-id="dcf60-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcf60-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcf60-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcf60-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcf60-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcf60-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcf60-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcf60-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf60-115">См. также</span><span class="sxs-lookup"><span data-stu-id="dcf60-115">See also</span></span>

- [<span data-ttu-id="dcf60-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="dcf60-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
