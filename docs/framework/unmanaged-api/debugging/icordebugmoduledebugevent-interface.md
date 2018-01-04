---
title: "Интерфейс ICorDebugModuleDebugEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86cf571180b2df15077547fac3d5dd058dbee83b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="0ba24-102">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="0ba24-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="0ba24-103">Расширяет [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) интерфейс для поддержки событий на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="0ba24-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ba24-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0ba24-104">Methods</span></span>  
  
|<span data-ttu-id="0ba24-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0ba24-105">Method</span></span>|<span data-ttu-id="0ba24-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="0ba24-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ba24-107">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="0ba24-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="0ba24-108">Возвращает объединенный модуль, который только что был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="0ba24-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ba24-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ba24-109">Remarks</span></span>  
 <span data-ttu-id="0ba24-110">[MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) и [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) этот интерфейс реализуют типы событий.</span><span class="sxs-lookup"><span data-stu-id="0ba24-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ba24-111">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="0ba24-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="0ba24-112">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0ba24-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ba24-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0ba24-113">Requirements</span></span>  
 <span data-ttu-id="0ba24-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ba24-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ba24-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ba24-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ba24-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ba24-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ba24-117">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ba24-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ba24-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0ba24-118">See Also</span></span>  
 [<span data-ttu-id="0ba24-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0ba24-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0ba24-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="0ba24-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
