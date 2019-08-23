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
ms.openlocfilehash: d2e01a5cf2b2aa25e91ebf0f8e3927858b12bea3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967569"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="7ab24-102">Перечисление CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="7ab24-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="7ab24-103">Указывает тип события, сведения о котором декодированы методом [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7ab24-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ab24-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="7ab24-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7ab24-105">Members</span></span>  
  
|<span data-ttu-id="7ab24-106">Член</span><span class="sxs-lookup"><span data-stu-id="7ab24-106">Member</span></span>|<span data-ttu-id="7ab24-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7ab24-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="7ab24-108">Событие загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="7ab24-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="7ab24-109">Событие выгрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="7ab24-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="7ab24-110">Первичное исключение.</span><span class="sxs-lookup"><span data-stu-id="7ab24-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="7ab24-111">Первичное исключение пользователя.</span><span class="sxs-lookup"><span data-stu-id="7ab24-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="7ab24-112">Исключение, для которого существует обработчик `catch`.</span><span class="sxs-lookup"><span data-stu-id="7ab24-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="7ab24-113">Необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="7ab24-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ab24-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ab24-114">Remarks</span></span>  
 <span data-ttu-id="7ab24-115">Член `CorDebugDebugEventKind` перечисления возвращается путем вызова метода [ICorDebugDebugEvent:: GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7ab24-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ab24-116">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7ab24-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ab24-117">Требования</span><span class="sxs-lookup"><span data-stu-id="7ab24-117">Requirements</span></span>  
 <span data-ttu-id="7ab24-118">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ab24-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ab24-119">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7ab24-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ab24-120">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="7ab24-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ab24-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ab24-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab24-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7ab24-122">See also</span></span>

- [<span data-ttu-id="7ab24-123">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="7ab24-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
