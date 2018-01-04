---
title: "ICorDebugObjectValue интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue
helpviewer_keywords: ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6dfde9f212936b1a0d0f5a6e76eafd4a2e62356c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvalue-interface1"></a><span data-ttu-id="931e6-102">ICorDebugObjectValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="931e6-102">ICorDebugObjectValue Interface1</span></span>
<span data-ttu-id="931e6-103">Подкласс «ICorDebugValue», который представляет значение, которое содержит объект.</span><span class="sxs-lookup"><span data-stu-id="931e6-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="931e6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="931e6-104">Methods</span></span>  
  
|<span data-ttu-id="931e6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="931e6-105">Method</span></span>|<span data-ttu-id="931e6-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="931e6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="931e6-107">Метод GetClass</span><span class="sxs-lookup"><span data-stu-id="931e6-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="931e6-108">Возвращает указатель на интерфейс для общеязыковой среды выполнения (CLR) <xref:System.Type> объекта этим `ICorDebugObjectValue` ссылки.</span><span class="sxs-lookup"><span data-stu-id="931e6-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="931e6-109">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="931e6-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="931e6-110">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="931e6-110">Not implemented.</span></span>|  
|[<span data-ttu-id="931e6-111">Метод GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="931e6-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="931e6-112">Возвращает указатель интерфейса [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) , представляющий значение заданного поля указанного класса.</span><span class="sxs-lookup"><span data-stu-id="931e6-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="931e6-113">Метод GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="931e6-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="931e6-114">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="931e6-114">Obsolete.</span></span> <span data-ttu-id="931e6-115">Не вызывайте этот метод.</span><span class="sxs-lookup"><span data-stu-id="931e6-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="931e6-116">Метод GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="931e6-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="931e6-117">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="931e6-117">Not implemented.</span></span>|  
|[<span data-ttu-id="931e6-118">Метод IsValueClass</span><span class="sxs-lookup"><span data-stu-id="931e6-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="931e6-119">Возвращает значение, указывающее, является ли объект ссылается этот `ICorDebugObjectValue` является типом значения.</span><span class="sxs-lookup"><span data-stu-id="931e6-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="931e6-120">Метод SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="931e6-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="931e6-121">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="931e6-121">Obsolete.</span></span> <span data-ttu-id="931e6-122">Не вызывайте этот метод.</span><span class="sxs-lookup"><span data-stu-id="931e6-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="931e6-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="931e6-123">Remarks</span></span>  
 <span data-ttu-id="931e6-124">`ICorDebugObjectValue` Остается действительным, пока не будет продолжен отлаживаемый процесс.</span><span class="sxs-lookup"><span data-stu-id="931e6-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="931e6-125">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="931e6-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="931e6-126">Требования</span><span class="sxs-lookup"><span data-stu-id="931e6-126">Requirements</span></span>  
 <span data-ttu-id="931e6-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="931e6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="931e6-128">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="931e6-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="931e6-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="931e6-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="931e6-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="931e6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="931e6-131">См. также</span><span class="sxs-lookup"><span data-stu-id="931e6-131">See Also</span></span>  
 [<span data-ttu-id="931e6-132">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="931e6-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 
