---
title: Перечисление LoggingLevelEnum
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
ms.openlocfilehash: 01e1eafd9955a0876f77e34eb73c2a3fc6d815c2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139207"
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="85f05-102">Перечисление LoggingLevelEnum</span><span class="sxs-lookup"><span data-stu-id="85f05-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="85f05-103">Указывает уровень важности описательного сообщения, записанного в журнале событий при регистрации события управляемым потоком.</span><span class="sxs-lookup"><span data-stu-id="85f05-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85f05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85f05-104">Syntax</span></span>  
  
```cpp  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="85f05-105">Члены</span><span class="sxs-lookup"><span data-stu-id="85f05-105">Members</span></span>  
  
|<span data-ttu-id="85f05-106">Член</span><span class="sxs-lookup"><span data-stu-id="85f05-106">Member</span></span>|<span data-ttu-id="85f05-107">Описание</span><span class="sxs-lookup"><span data-stu-id="85f05-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="85f05-108">Сообщение является уровнем трассировки 0.</span><span class="sxs-lookup"><span data-stu-id="85f05-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="85f05-109">Сообщение является уровнем трассировки 1.</span><span class="sxs-lookup"><span data-stu-id="85f05-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="85f05-110">Сообщение является уровнем трассировки 2.</span><span class="sxs-lookup"><span data-stu-id="85f05-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="85f05-111">Сообщение имеет уровень трассировки 3.</span><span class="sxs-lookup"><span data-stu-id="85f05-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="85f05-112">Сообщение имеет уровень трассировки 4.</span><span class="sxs-lookup"><span data-stu-id="85f05-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="85f05-113">Сообщение имеет уровень состояния 0.</span><span class="sxs-lookup"><span data-stu-id="85f05-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="85f05-114">Сообщение имеет уровень состояния 1.</span><span class="sxs-lookup"><span data-stu-id="85f05-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="85f05-115">Сообщение имеет уровень состояния 2.</span><span class="sxs-lookup"><span data-stu-id="85f05-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="85f05-116">Сообщение имеет уровень состояния 3.</span><span class="sxs-lookup"><span data-stu-id="85f05-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="85f05-117">Сообщение имеет уровень состояния 4.</span><span class="sxs-lookup"><span data-stu-id="85f05-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="85f05-118">Сообщение является уровнем предупреждения.</span><span class="sxs-lookup"><span data-stu-id="85f05-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="85f05-119">Сообщение имеет уровень ошибки.</span><span class="sxs-lookup"><span data-stu-id="85f05-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="85f05-120">Сообщение имеет уровень тревоги.</span><span class="sxs-lookup"><span data-stu-id="85f05-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85f05-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="85f05-121">Remarks</span></span>  
 <span data-ttu-id="85f05-122">Среда CLR вызывает метод [ICorDebugManagedCallback:: LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) , чтобы уведомить отладчик о том, что управляемый поток зарегистрировал событие.</span><span class="sxs-lookup"><span data-stu-id="85f05-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="85f05-123">Среда CLR передает значение перечисления `LoggingLevelEnum`, чтобы указать степень серьезности сообщения, которое управляемый поток записал в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="85f05-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85f05-124">Требования</span><span class="sxs-lookup"><span data-stu-id="85f05-124">Requirements</span></span>  
 <span data-ttu-id="85f05-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85f05-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85f05-126">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85f05-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85f05-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85f05-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85f05-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85f05-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f05-129">См. также</span><span class="sxs-lookup"><span data-stu-id="85f05-129">See also</span></span>

- <xref:System.Diagnostics.EventLog>
- [<span data-ttu-id="85f05-130">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="85f05-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
