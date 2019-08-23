---
title: Интерфейс ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 706f392652c5cb868e09d4ee9fcb69c6d3d92d2a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965099"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="9b611-102">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="9b611-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="9b611-103">Расширяет интерфейс [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) для поддержки событий уровня модуля.</span><span class="sxs-lookup"><span data-stu-id="9b611-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b611-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9b611-104">Methods</span></span>  
  
|<span data-ttu-id="9b611-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9b611-105">Method</span></span>|<span data-ttu-id="9b611-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9b611-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9b611-107">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="9b611-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="9b611-108">Возвращает объединенный модуль, который только что был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="9b611-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b611-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b611-109">Remarks</span></span>  
 <span data-ttu-id="9b611-110">Типы событий [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) и [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) реализуют этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9b611-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b611-111">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="9b611-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="9b611-112">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9b611-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b611-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9b611-113">Requirements</span></span>  
 <span data-ttu-id="9b611-114">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b611-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b611-115">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9b611-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b611-116">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="9b611-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b611-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b611-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b611-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9b611-118">See also</span></span>

- [<span data-ttu-id="9b611-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9b611-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9b611-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="9b611-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
