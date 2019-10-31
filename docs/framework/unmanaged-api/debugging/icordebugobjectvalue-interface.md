---
title: Интерфейс ICorDebugObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: b782207503a2c3f739a30f68d509e6b481d2b6a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129750"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="195e4-102">Интерфейс ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="195e4-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="195e4-103">Подкласс "ICorDebugValue", представляющий значение, которое содержит объект.</span><span class="sxs-lookup"><span data-stu-id="195e4-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="195e4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="195e4-104">Methods</span></span>  
  
|<span data-ttu-id="195e4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="195e4-105">Method</span></span>|<span data-ttu-id="195e4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="195e4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="195e4-107">Метод GetClass</span><span class="sxs-lookup"><span data-stu-id="195e4-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="195e4-108">Возвращает указатель интерфейса на <xref:System.Type> среды CLR объекта, на который ссылается этот `ICorDebugObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="195e4-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="195e4-109">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="195e4-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="195e4-110">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="195e4-110">Not implemented.</span></span>|  
|[<span data-ttu-id="195e4-111">Метод GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="195e4-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="195e4-112">Возвращает указатель интерфейса на объект [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) , представляющий значение указанного поля указанного класса.</span><span class="sxs-lookup"><span data-stu-id="195e4-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="195e4-113">Метод GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="195e4-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="195e4-114">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="195e4-114">Obsolete.</span></span> <span data-ttu-id="195e4-115">Не вызывайте этот метод.</span><span class="sxs-lookup"><span data-stu-id="195e4-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="195e4-116">Метод GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="195e4-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="195e4-117">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="195e4-117">Not implemented.</span></span>|  
|[<span data-ttu-id="195e4-118">Метод IsValueClass</span><span class="sxs-lookup"><span data-stu-id="195e4-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="195e4-119">Возвращает значение, указывающее, является ли объект, на который ссылается данный `ICorDebugObjectValue`, типом значения.</span><span class="sxs-lookup"><span data-stu-id="195e4-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="195e4-120">Метод SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="195e4-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="195e4-121">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="195e4-121">Obsolete.</span></span> <span data-ttu-id="195e4-122">Не вызывайте этот метод.</span><span class="sxs-lookup"><span data-stu-id="195e4-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="195e4-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="195e4-123">Remarks</span></span>  
 <span data-ttu-id="195e4-124">`ICorDebugObjectValue` остается действительным до тех пор, пока отлаживаемый процесс не будет продолжен.</span><span class="sxs-lookup"><span data-stu-id="195e4-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="195e4-125">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="195e4-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="195e4-126">Требования</span><span class="sxs-lookup"><span data-stu-id="195e4-126">Requirements</span></span>  
 <span data-ttu-id="195e4-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="195e4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="195e4-128">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="195e4-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="195e4-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="195e4-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="195e4-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="195e4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195e4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="195e4-131">See also</span></span>

- [<span data-ttu-id="195e4-132">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="195e4-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
