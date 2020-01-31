---
title: Интерфейс ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: a2c7eaa8a2c811c1696024d9af4b715cc49e7caa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792900"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="8b027-102">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="8b027-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="8b027-103">Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий уровня модуля.</span><span class="sxs-lookup"><span data-stu-id="8b027-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b027-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8b027-104">Methods</span></span>  
  
|<span data-ttu-id="8b027-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8b027-105">Method</span></span>|<span data-ttu-id="8b027-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8b027-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b027-107">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="8b027-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="8b027-108">Возвращает объединенный модуль, который только что был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="8b027-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b027-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="8b027-109">Remarks</span></span>  
 <span data-ttu-id="8b027-110">Типы событий [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) и [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) реализуют этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8b027-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b027-111">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8b027-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="8b027-112">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8b027-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b027-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8b027-113">Requirements</span></span>  
 <span data-ttu-id="8b027-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b027-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b027-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b027-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b027-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b027-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b027-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b027-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b027-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b027-118">See also</span></span>

- [<span data-ttu-id="8b027-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8b027-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8b027-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="8b027-120">Debugging</span></span>](index.md)
