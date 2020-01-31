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
ms.openlocfilehash: e714c41812c8aaccd713115712df05744cc015e3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789385"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="3e00c-102">Перечисление CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="3e00c-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="3e00c-103">Указывает событие, о котором сообщает обратный вызов во время фазы перемотки.</span><span class="sxs-lookup"><span data-stu-id="3e00c-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e00c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e00c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="3e00c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3e00c-105">Members</span></span>  
  
|<span data-ttu-id="3e00c-106">Член</span><span class="sxs-lookup"><span data-stu-id="3e00c-106">Member</span></span>|<span data-ttu-id="3e00c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3e00c-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="3e00c-108">Начало процесса очистки.</span><span class="sxs-lookup"><span data-stu-id="3e00c-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="3e00c-109">Исключение перехвачено.</span><span class="sxs-lookup"><span data-stu-id="3e00c-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3e00c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3e00c-110">Requirements</span></span>  
 <span data-ttu-id="3e00c-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e00c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e00c-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e00c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e00c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e00c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e00c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e00c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e00c-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e00c-115">See also</span></span>

- [<span data-ttu-id="3e00c-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="3e00c-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
