---
title: "Интерфейс ICorDebugDebugEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b4422b165f06b60dedff95fc3de58e5627db7fac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="c8776-102">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c8776-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="c8776-103">Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="c8776-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8776-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c8776-104">Methods</span></span>  
  
|<span data-ttu-id="c8776-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c8776-105">Method</span></span>|<span data-ttu-id="c8776-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c8776-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8776-107">Метод GetEventKind</span><span class="sxs-lookup"><span data-stu-id="c8776-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="c8776-108">Указывает тип события, который представляет этот объект `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="c8776-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="c8776-109">Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="c8776-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="c8776-110">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="c8776-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8776-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c8776-111">Remarks</span></span>  
 <span data-ttu-id="c8776-112">Следующие интерфейсы являются производными от интерфейса `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="c8776-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
-   [<span data-ttu-id="c8776-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c8776-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
-   [<span data-ttu-id="c8776-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c8776-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="c8776-115">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="c8776-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="c8776-116">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c8776-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8776-117">Требования</span><span class="sxs-lookup"><span data-stu-id="c8776-117">Requirements</span></span>  
 <span data-ttu-id="c8776-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8776-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8776-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8776-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8776-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8776-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8776-121">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8776-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8776-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c8776-122">See Also</span></span>  
 [<span data-ttu-id="c8776-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c8776-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c8776-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="c8776-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
