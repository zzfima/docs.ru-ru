---
title: Интерфейс ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: ea42faa4001fa880354690df1551de3be767e683
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137038"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="07c1c-102">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="07c1c-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="07c1c-103">Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="07c1c-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07c1c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="07c1c-104">Methods</span></span>  
  
|<span data-ttu-id="07c1c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="07c1c-105">Method</span></span>|<span data-ttu-id="07c1c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="07c1c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07c1c-107">Метод GetEventKind</span><span class="sxs-lookup"><span data-stu-id="07c1c-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="07c1c-108">Указывает тип события, который представляет этот объект `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="07c1c-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="07c1c-109">Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="07c1c-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="07c1c-110">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="07c1c-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07c1c-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="07c1c-111">Remarks</span></span>  
 <span data-ttu-id="07c1c-112">Следующие интерфейсы являются производными от интерфейса `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="07c1c-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="07c1c-113">икордебужексцептиондебужевент</span><span class="sxs-lookup"><span data-stu-id="07c1c-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="07c1c-114">икордебугмодуледебужевент</span><span class="sxs-lookup"><span data-stu-id="07c1c-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="07c1c-115">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="07c1c-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="07c1c-116">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="07c1c-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07c1c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="07c1c-117">Requirements</span></span>  
 <span data-ttu-id="07c1c-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07c1c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07c1c-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07c1c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07c1c-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07c1c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07c1c-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07c1c-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07c1c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="07c1c-122">See also</span></span>

- [<span data-ttu-id="07c1c-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="07c1c-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="07c1c-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="07c1c-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
