---
title: "Перечисление CorDebugExceptionUnwindCallbackType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugExceptionUnwindCallbackType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugExceptionUnwindCallbackType
helpviewer_keywords: CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c5ee074e55d0d407f89c778c579aa5c4ce03a10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="eea7e-102">Перечисление CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="eea7e-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="eea7e-103">Указывает событие, о котором сообщает обратный вызов во время фазы перемотки.</span><span class="sxs-lookup"><span data-stu-id="eea7e-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eea7e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eea7e-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="eea7e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="eea7e-105">Members</span></span>  
  
|<span data-ttu-id="eea7e-106">Член</span><span class="sxs-lookup"><span data-stu-id="eea7e-106">Member</span></span>|<span data-ttu-id="eea7e-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="eea7e-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="eea7e-108">Начало процесса очистки.</span><span class="sxs-lookup"><span data-stu-id="eea7e-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="eea7e-109">Было перехвачено исключение.</span><span class="sxs-lookup"><span data-stu-id="eea7e-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eea7e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="eea7e-110">Requirements</span></span>  
 <span data-ttu-id="eea7e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eea7e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eea7e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eea7e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eea7e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eea7e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eea7e-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eea7e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eea7e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="eea7e-115">See Also</span></span>  
 [<span data-ttu-id="eea7e-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="eea7e-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
