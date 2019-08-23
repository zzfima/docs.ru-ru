---
title: Интерфейс ICorDebugReferenceValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67006603747abd89f1b635c065860dcbe1c47a29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965646"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="89123-102">Интерфейс ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="89123-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="89123-103">Предоставляет методы, управляющие значением, которое является ссылкой на объект.</span><span class="sxs-lookup"><span data-stu-id="89123-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="89123-104">(Т. е. Этот интерфейс предоставляет методы, управляющие указателем.) Этот интерфейс реализует "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="89123-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89123-105">Методы</span><span class="sxs-lookup"><span data-stu-id="89123-105">Methods</span></span>  
  
|<span data-ttu-id="89123-106">Метод</span><span class="sxs-lookup"><span data-stu-id="89123-106">Method</span></span>|<span data-ttu-id="89123-107">Описание</span><span class="sxs-lookup"><span data-stu-id="89123-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89123-108">Метод Dereference</span><span class="sxs-lookup"><span data-stu-id="89123-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="89123-109">Возвращает объект, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="89123-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="89123-110">Метод DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="89123-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="89123-111">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="89123-111">Not implemented.</span></span> <span data-ttu-id="89123-112">Не вызывайте этот метод.</span><span class="sxs-lookup"><span data-stu-id="89123-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="89123-113">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="89123-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="89123-114">Возвращает текущий адрес памяти объекта, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="89123-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="89123-115">Метод IsNull</span><span class="sxs-lookup"><span data-stu-id="89123-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="89123-116">Возвращает значение, указывающее, `ICorDebugReferenceValue` является ли значение значением NULL, в этом случае, `ICorDebugReferenceValue` не указывает на объект.</span><span class="sxs-lookup"><span data-stu-id="89123-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="89123-117">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="89123-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="89123-118">Задает текущий адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="89123-118">Sets the current memory address.</span></span> <span data-ttu-id="89123-119">Это значит, что этот метод задает `ICorDebugReferenceValue` значение, которое указывает на объект.</span><span class="sxs-lookup"><span data-stu-id="89123-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89123-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="89123-120">Remarks</span></span>  
 <span data-ttu-id="89123-121">Среда CLR может выполнять сборку мусора для объектов при продолжении отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="89123-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="89123-122">Сборка мусора может перемещать объекты в памяти.</span><span class="sxs-lookup"><span data-stu-id="89123-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="89123-123">`ICorDebugReferenceValue` Либо взаимодействуют со сборкой мусора, так что ее сведения обновляются после сборки мусора, или же она становится неявной до сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="89123-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="89123-124">После продолжения отлаживаемого процесса объектможетбытьнеявнонедействительным.`ICorDebugReferenceValue`</span><span class="sxs-lookup"><span data-stu-id="89123-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="89123-125">Производный "ICorDebugHandleValue" не является недействительным до тех пор, пока он не будет явно освобожден или открыт.</span><span class="sxs-lookup"><span data-stu-id="89123-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89123-126">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="89123-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89123-127">Требования</span><span class="sxs-lookup"><span data-stu-id="89123-127">Requirements</span></span>  
 <span data-ttu-id="89123-128">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89123-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89123-129">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="89123-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89123-130">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="89123-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89123-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89123-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89123-132">См. также</span><span class="sxs-lookup"><span data-stu-id="89123-132">See also</span></span>

- [<span data-ttu-id="89123-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="89123-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
