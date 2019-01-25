---
title: Перечисление CorDebugExceptionCallbackType
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e9a3b0320ac0be785f0823afef1819ab8a35eb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585553"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="0a34d-102">Перечисление CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="0a34d-102">CorDebugExceptionCallbackType Enumeration</span></span>
<span data-ttu-id="0a34d-103">Указывает тип обратного вызова, состоящее из [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) событий.</span><span class="sxs-lookup"><span data-stu-id="0a34d-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a34d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a34d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="0a34d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0a34d-105">Members</span></span>  
  
|<span data-ttu-id="0a34d-106">Член</span><span class="sxs-lookup"><span data-stu-id="0a34d-106">Member</span></span>|<span data-ttu-id="0a34d-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0a34d-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="0a34d-108">Возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="0a34d-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="0a34d-109">В процессе очистки исключения ввода пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="0a34d-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="0a34d-110">В процессе очистки исключения найден `catch` блока в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="0a34d-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="0a34d-111">Исключение не обработано.</span><span class="sxs-lookup"><span data-stu-id="0a34d-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a34d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0a34d-112">Requirements</span></span>  
 <span data-ttu-id="0a34d-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a34d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a34d-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a34d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a34d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a34d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a34d-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a34d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a34d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0a34d-117">See also</span></span>
- [<span data-ttu-id="0a34d-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="0a34d-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
