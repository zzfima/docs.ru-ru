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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cae8a695ccf313b846c8860309c3461a821fe38
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977218"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="cff66-102">Интерфейс ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="cff66-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="cff66-103">Подкласс «ICorDebugValue», который представляет значение, которое содержит объект.</span><span class="sxs-lookup"><span data-stu-id="cff66-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cff66-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cff66-104">Methods</span></span>  
  
|<span data-ttu-id="cff66-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cff66-105">Method</span></span>|<span data-ttu-id="cff66-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="cff66-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cff66-107">Метод GetClass</span><span class="sxs-lookup"><span data-stu-id="cff66-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="cff66-108">Получает указатель интерфейса для общеязыковой среды выполнения (CLR) <xref:System.Type> объекта, `ICorDebugObjectValue` ссылки.</span><span class="sxs-lookup"><span data-stu-id="cff66-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="cff66-109">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="cff66-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="cff66-110">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="cff66-110">Not implemented.</span></span>|  
|[<span data-ttu-id="cff66-111">Метод GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="cff66-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="cff66-112">Получает указатель интерфейса на [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) , представляющий значение заданного поля указанного класса.</span><span class="sxs-lookup"><span data-stu-id="cff66-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="cff66-113">Метод GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="cff66-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="cff66-114">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="cff66-114">Obsolete.</span></span> <span data-ttu-id="cff66-115">Этот метод не вызывается.</span><span class="sxs-lookup"><span data-stu-id="cff66-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="cff66-116">Метод GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="cff66-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="cff66-117">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="cff66-117">Not implemented.</span></span>|  
|[<span data-ttu-id="cff66-118">Метод IsValueClass</span><span class="sxs-lookup"><span data-stu-id="cff66-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="cff66-119">Получает значение, указывающее, является ли объект ссылается этот `ICorDebugObjectValue` является типом значения.</span><span class="sxs-lookup"><span data-stu-id="cff66-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="cff66-120">Метод SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="cff66-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="cff66-121">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="cff66-121">Obsolete.</span></span> <span data-ttu-id="cff66-122">Этот метод не вызывается.</span><span class="sxs-lookup"><span data-stu-id="cff66-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cff66-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="cff66-123">Remarks</span></span>  
 <span data-ttu-id="cff66-124">`ICorDebugObjectValue` Остается действительным, пока продолжается отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="cff66-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cff66-125">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="cff66-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cff66-126">Требования</span><span class="sxs-lookup"><span data-stu-id="cff66-126">Requirements</span></span>  
 <span data-ttu-id="cff66-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cff66-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cff66-128">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cff66-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cff66-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cff66-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cff66-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cff66-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff66-131">См. также</span><span class="sxs-lookup"><span data-stu-id="cff66-131">See also</span></span>
- [<span data-ttu-id="cff66-132">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="cff66-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

