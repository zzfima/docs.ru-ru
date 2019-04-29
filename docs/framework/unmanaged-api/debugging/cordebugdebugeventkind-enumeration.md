---
title: Перечисление CorDebugDebugEventKind
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e5479fad3f19c219a0ca1d5d01934ce92a7162e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609247"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="54799-102">Перечисление CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="54799-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="54799-103">Указывает тип события, сведения о котором декодируется [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="54799-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54799-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54799-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="54799-105">Участники</span><span class="sxs-lookup"><span data-stu-id="54799-105">Members</span></span>  
  
|<span data-ttu-id="54799-106">Член</span><span class="sxs-lookup"><span data-stu-id="54799-106">Member</span></span>|<span data-ttu-id="54799-107">Описание</span><span class="sxs-lookup"><span data-stu-id="54799-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="54799-108">Событие загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="54799-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="54799-109">Событие выгрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="54799-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="54799-110">Первичное исключение.</span><span class="sxs-lookup"><span data-stu-id="54799-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="54799-111">Первичное исключение пользователя.</span><span class="sxs-lookup"><span data-stu-id="54799-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="54799-112">Исключение, для которого существует обработчик `catch`.</span><span class="sxs-lookup"><span data-stu-id="54799-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="54799-113">Необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="54799-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54799-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="54799-114">Remarks</span></span>  
 <span data-ttu-id="54799-115">Является членом `CorDebugDebugEventKind` перечисление возвращается путем вызова [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="54799-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54799-116">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="54799-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54799-117">Требования</span><span class="sxs-lookup"><span data-stu-id="54799-117">Requirements</span></span>  
 <span data-ttu-id="54799-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54799-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54799-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54799-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54799-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54799-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54799-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54799-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54799-122">См. также</span><span class="sxs-lookup"><span data-stu-id="54799-122">See also</span></span>

- [<span data-ttu-id="54799-123">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="54799-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
