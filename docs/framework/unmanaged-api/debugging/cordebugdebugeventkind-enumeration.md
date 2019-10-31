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
ms.openlocfilehash: de4ac1f39ea9cfb4b616bd4e2c85e5de530dbb0b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132230"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="a93b0-102">Перечисление CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="a93b0-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="a93b0-103">Указывает тип события, сведения о котором декодированы методом [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a93b0-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a93b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a93b0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="a93b0-105">Члены</span><span class="sxs-lookup"><span data-stu-id="a93b0-105">Members</span></span>  
  
|<span data-ttu-id="a93b0-106">Член</span><span class="sxs-lookup"><span data-stu-id="a93b0-106">Member</span></span>|<span data-ttu-id="a93b0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a93b0-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="a93b0-108">Событие загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="a93b0-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="a93b0-109">Событие выгрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="a93b0-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="a93b0-110">Первичное исключение.</span><span class="sxs-lookup"><span data-stu-id="a93b0-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="a93b0-111">Первичное исключение пользователя.</span><span class="sxs-lookup"><span data-stu-id="a93b0-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="a93b0-112">Исключение, для которого существует обработчик `catch`.</span><span class="sxs-lookup"><span data-stu-id="a93b0-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="a93b0-113">Необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="a93b0-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a93b0-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="a93b0-114">Remarks</span></span>  
 <span data-ttu-id="a93b0-115">Член перечисления `CorDebugDebugEventKind` возвращается путем вызова метода [ICorDebugDebugEvent:: GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a93b0-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a93b0-116">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a93b0-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a93b0-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a93b0-117">Requirements</span></span>  
 <span data-ttu-id="a93b0-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a93b0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a93b0-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a93b0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a93b0-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a93b0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a93b0-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a93b0-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93b0-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a93b0-122">See also</span></span>

- [<span data-ttu-id="a93b0-123">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="a93b0-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
