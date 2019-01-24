---
title: Интерфейс ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 399f27db0a2d18e3bcd90b87f4470a77cb50595d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646869"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="7277f-102">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="7277f-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="7277f-103">Расширяет [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) интерфейс для поддержки событий на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="7277f-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7277f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7277f-104">Methods</span></span>  
  
|<span data-ttu-id="7277f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7277f-105">Method</span></span>|<span data-ttu-id="7277f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7277f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7277f-107">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="7277f-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="7277f-108">Возвращает объединенный модуль, который только что был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="7277f-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7277f-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7277f-109">Remarks</span></span>  
 <span data-ttu-id="7277f-110">[MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) и [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) этот интерфейс реализуют типы событий.</span><span class="sxs-lookup"><span data-stu-id="7277f-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7277f-111">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="7277f-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="7277f-112">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7277f-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7277f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7277f-113">Requirements</span></span>  
 <span data-ttu-id="7277f-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7277f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7277f-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7277f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7277f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7277f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7277f-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7277f-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7277f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7277f-118">See also</span></span>
- [<span data-ttu-id="7277f-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7277f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7277f-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="7277f-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
