---
title: Интерфейс ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 550cb6379ef0d5d17a3446b3f21120208b5a3dad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989174"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="f1c87-102">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="f1c87-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="f1c87-103">Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="f1c87-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1c87-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f1c87-104">Methods</span></span>  
  
|<span data-ttu-id="f1c87-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f1c87-105">Method</span></span>|<span data-ttu-id="f1c87-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f1c87-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1c87-107">Метод GetEventKind</span><span class="sxs-lookup"><span data-stu-id="f1c87-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="f1c87-108">Указывает тип события, который представляет этот объект `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="f1c87-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="f1c87-109">Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="f1c87-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="f1c87-110">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="f1c87-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1c87-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f1c87-111">Remarks</span></span>  
 <span data-ttu-id="f1c87-112">Следующие интерфейсы являются производными от интерфейса `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="f1c87-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="f1c87-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="f1c87-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="f1c87-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="f1c87-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="f1c87-115">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="f1c87-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="f1c87-116">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f1c87-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1c87-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f1c87-117">Requirements</span></span>  
 <span data-ttu-id="f1c87-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1c87-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1c87-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1c87-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1c87-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1c87-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1c87-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1c87-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c87-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f1c87-122">See also</span></span>

- [<span data-ttu-id="f1c87-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f1c87-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f1c87-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="f1c87-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
