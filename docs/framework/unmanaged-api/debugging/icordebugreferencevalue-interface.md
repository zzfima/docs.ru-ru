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
ms.openlocfilehash: d6575acfb1f75cbc8e3d59ddca5fea0953274cf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782958"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="e2ed7-102">Интерфейс ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="e2ed7-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="e2ed7-103">Предоставляет методы, управляющие значением, которое является ссылкой на объект.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="e2ed7-104">(То есть этот интерфейс предоставляет методы, управляющие указатель). Этот интерфейс реализует «ICorDebugValue».</span><span class="sxs-lookup"><span data-stu-id="e2ed7-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2ed7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e2ed7-105">Methods</span></span>  
  
|<span data-ttu-id="e2ed7-106">Метод</span><span class="sxs-lookup"><span data-stu-id="e2ed7-106">Method</span></span>|<span data-ttu-id="e2ed7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e2ed7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2ed7-108">Метод Dereference</span><span class="sxs-lookup"><span data-stu-id="e2ed7-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="e2ed7-109">Получает объект, на который приведена ссылка.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="e2ed7-110">Метод DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="e2ed7-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="e2ed7-111">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-111">Not implemented.</span></span> <span data-ttu-id="e2ed7-112">Этот метод не вызывается.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="e2ed7-113">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="e2ed7-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="e2ed7-114">Получает текущий адрес памяти объекта, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="e2ed7-115">Метод IsNull</span><span class="sxs-lookup"><span data-stu-id="e2ed7-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="e2ed7-116">Получает значение, указывающее, является ли это `ICorDebugReferenceValue` имеет значение null, в этом случае `ICorDebugReferenceValue` не указывает на объект.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="e2ed7-117">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="e2ed7-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="e2ed7-118">Задает текущий адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-118">Sets the current memory address.</span></span> <span data-ttu-id="e2ed7-119">То есть, этот метод устанавливает это `ICorDebugReferenceValue` для указания на объект.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2ed7-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2ed7-120">Remarks</span></span>  
 <span data-ttu-id="e2ed7-121">Среда CLR (CLR) может сделать сбор мусора для объектов, когда продолжает выполнение отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="e2ed7-122">Сборка мусора может перемещать объекты в памяти.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="e2ed7-123">`ICorDebugReferenceValue` Будет либо сотрудничать со сборкой мусора, чтобы его сведения обновляются после сборки мусора, или он будет недействительным неявно перед сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="e2ed7-124">`ICorDebugReferenceValue` Объект может быть неявно недействительными после возобновлена отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="e2ed7-125">Производный «ICorDebugHandleValue» не является недействительным, пока не будет явно выпуска или предоставляются.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2ed7-126">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="e2ed7-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ed7-127">Требования</span><span class="sxs-lookup"><span data-stu-id="e2ed7-127">Requirements</span></span>  
 <span data-ttu-id="e2ed7-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2ed7-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2ed7-129">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2ed7-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2ed7-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2ed7-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2ed7-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2ed7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ed7-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e2ed7-132">See also</span></span>

- [<span data-ttu-id="e2ed7-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e2ed7-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
