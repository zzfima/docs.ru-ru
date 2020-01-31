---
title: Интерфейс ICorDebugValue
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: e1044386bd6251132703c4e98a0cf2ed267d34e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791135"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="6b64c-102">Интерфейс ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="6b64c-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="6b64c-103">Представляет значение в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="6b64c-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="6b64c-104">Значением может быть значение Read или Write.</span><span class="sxs-lookup"><span data-stu-id="6b64c-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b64c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6b64c-105">Methods</span></span>  
  
|<span data-ttu-id="6b64c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="6b64c-106">Method</span></span>|<span data-ttu-id="6b64c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6b64c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b64c-108">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6b64c-108">CreateBreakpoint Method</span></span>](icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="6b64c-109">Этот метод в настоящее время не реализован.</span><span class="sxs-lookup"><span data-stu-id="6b64c-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="6b64c-110">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="6b64c-110">GetAddress Method</span></span>](icordebugvalue-getaddress-method.md)|<span data-ttu-id="6b64c-111">Возвращает адрес этого `ICorDebugValue` объекта, который находится в процессе отладки.</span><span class="sxs-lookup"><span data-stu-id="6b64c-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="6b64c-112">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="6b64c-112">GetSize Method</span></span>](icordebugvalue-getsize-method.md)|<span data-ttu-id="6b64c-113">Возвращает размер данного объекта `ICorDebugValue` в байтах.</span><span class="sxs-lookup"><span data-stu-id="6b64c-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="6b64c-114">Метод GetType</span><span class="sxs-lookup"><span data-stu-id="6b64c-114">GetType Method</span></span>](icordebugvalue-gettype-method.md)|<span data-ttu-id="6b64c-115">Возвращает тип примитива данного объекта `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="6b64c-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b64c-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="6b64c-116">Remarks</span></span>  
 <span data-ttu-id="6b64c-117">В общем случае владение объектом значения передается при его возврате.</span><span class="sxs-lookup"><span data-stu-id="6b64c-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="6b64c-118">Получатель отвечает за удаление ссылки из объекта после завершения работы с объектом.</span><span class="sxs-lookup"><span data-stu-id="6b64c-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="6b64c-119">В зависимости от того, откуда было получено значение, оно может остаться недействительным после возобновления процесса.</span><span class="sxs-lookup"><span data-stu-id="6b64c-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="6b64c-120">Поэтому в общем случае значение не должно удерживаться в вызове метода [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6b64c-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b64c-121">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="6b64c-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b64c-122">Требования</span><span class="sxs-lookup"><span data-stu-id="6b64c-122">Requirements</span></span>  
 <span data-ttu-id="6b64c-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b64c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b64c-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b64c-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b64c-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b64c-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b64c-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b64c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b64c-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="6b64c-127">See also</span></span>

- [<span data-ttu-id="6b64c-128">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="6b64c-128">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="6b64c-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6b64c-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
