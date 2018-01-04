---
title: "ICorDebugReferenceValue интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue
helpviewer_keywords: ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ac6260a601f7fdacf84034a6ae83c9423fafa11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevalue-interface1"></a><span data-ttu-id="e3848-102">ICorDebugReferenceValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="e3848-102">ICorDebugReferenceValue Interface1</span></span>
<span data-ttu-id="e3848-103">Предоставляет методы, управляющие значением, которое является ссылкой на объект.</span><span class="sxs-lookup"><span data-stu-id="e3848-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="e3848-104">(То есть этот интерфейс предоставляет методы, управляющие указателя). Этот интерфейс реализует «ICorDebugValue».</span><span class="sxs-lookup"><span data-stu-id="e3848-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3848-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e3848-105">Methods</span></span>  
  
|<span data-ttu-id="e3848-106">Метод</span><span class="sxs-lookup"><span data-stu-id="e3848-106">Method</span></span>|<span data-ttu-id="e3848-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="e3848-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3848-108">Метод Dereference</span><span class="sxs-lookup"><span data-stu-id="e3848-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="e3848-109">Возвращает объект, на который имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="e3848-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="e3848-110">Метод DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="e3848-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="e3848-111">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="e3848-111">Not implemented.</span></span> <span data-ttu-id="e3848-112">Не вызывайте этот метод.</span><span class="sxs-lookup"><span data-stu-id="e3848-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="e3848-113">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="e3848-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="e3848-114">Получает текущий адрес памяти объекта, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="e3848-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="e3848-115">Метод IsNull</span><span class="sxs-lookup"><span data-stu-id="e3848-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="e3848-116">Возвращает значение, указывающее, является ли это `ICorDebugReferenceValue` имеет значение null, в этом случае `ICorDebugReferenceValue` не указывает на объект.</span><span class="sxs-lookup"><span data-stu-id="e3848-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="e3848-117">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="e3848-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="e3848-118">Задает текущий адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="e3848-118">Sets the current memory address.</span></span> <span data-ttu-id="e3848-119">То есть этот метод задает это `ICorDebugReferenceValue` для указания на объект.</span><span class="sxs-lookup"><span data-stu-id="e3848-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3848-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="e3848-120">Remarks</span></span>  
 <span data-ttu-id="e3848-121">Общеязыковая среда выполнения (CLR) может выполнить сборку мусора для объектов после возобновления процесса отладки.</span><span class="sxs-lookup"><span data-stu-id="e3848-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="e3848-122">Сборка мусора может перемещаться объектов в памяти.</span><span class="sxs-lookup"><span data-stu-id="e3848-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="e3848-123">`ICorDebugReferenceValue` Будет либо взаимодействовать со сбором мусора, чтобы его данные обновляются после сборки мусора, или он будет неявно объявлен недействительным перед сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="e3848-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="e3848-124">`ICorDebugReferenceValue` Объект может быть объявлен недействительным неявным образом после возобновлена отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="e3848-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="e3848-125">Производный» ICorDebugHandleValue» становится недействительным, пока не будет явно выпуска или предоставляется.</span><span class="sxs-lookup"><span data-stu-id="e3848-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3848-126">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="e3848-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3848-127">Требования</span><span class="sxs-lookup"><span data-stu-id="e3848-127">Requirements</span></span>  
 <span data-ttu-id="e3848-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3848-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3848-129">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3848-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3848-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3848-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3848-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3848-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3848-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e3848-132">See Also</span></span>  
    
    
 [<span data-ttu-id="e3848-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e3848-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
