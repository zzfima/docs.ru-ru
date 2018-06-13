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
ms.openlocfilehash: 7fe2fcf10b517f4eb7b1c7e87142afb386821246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404124"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="17769-102">Перечисление CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="17769-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="17769-103">Указывает событие, о котором сообщает обратный вызов во время фазы перемотки.</span><span class="sxs-lookup"><span data-stu-id="17769-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17769-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17769-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="17769-105">Участники</span><span class="sxs-lookup"><span data-stu-id="17769-105">Members</span></span>  
  
|<span data-ttu-id="17769-106">Член</span><span class="sxs-lookup"><span data-stu-id="17769-106">Member</span></span>|<span data-ttu-id="17769-107">Описание</span><span class="sxs-lookup"><span data-stu-id="17769-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="17769-108">Начало процесса очистки.</span><span class="sxs-lookup"><span data-stu-id="17769-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="17769-109">Было перехвачено исключение.</span><span class="sxs-lookup"><span data-stu-id="17769-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="17769-110">Требования</span><span class="sxs-lookup"><span data-stu-id="17769-110">Requirements</span></span>  
 <span data-ttu-id="17769-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17769-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17769-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17769-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17769-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17769-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17769-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17769-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17769-115">См. также</span><span class="sxs-lookup"><span data-stu-id="17769-115">See Also</span></span>  
 [<span data-ttu-id="17769-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="17769-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
