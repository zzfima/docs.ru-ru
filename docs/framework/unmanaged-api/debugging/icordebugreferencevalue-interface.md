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
ms.openlocfilehash: 16d7b89ee441e8d634c36fb87185b3f2846860b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137712"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="5914a-102">Интерфейс ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="5914a-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="5914a-103">Предоставляет методы, управляющие значением, которое является ссылкой на объект.</span><span class="sxs-lookup"><span data-stu-id="5914a-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="5914a-104">(Т. е. Этот интерфейс предоставляет методы, управляющие указателем.) Этот интерфейс реализует "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="5914a-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5914a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5914a-105">Methods</span></span>  
  
|<span data-ttu-id="5914a-106">Метод</span><span class="sxs-lookup"><span data-stu-id="5914a-106">Method</span></span>|<span data-ttu-id="5914a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5914a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5914a-108">Метод Dereference</span><span class="sxs-lookup"><span data-stu-id="5914a-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="5914a-109">Возвращает объект, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="5914a-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="5914a-110">Метод DereferenceStrong</span><span class="sxs-lookup"><span data-stu-id="5914a-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="5914a-111">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="5914a-111">Not implemented.</span></span> <span data-ttu-id="5914a-112">Не вызывайте этот метод.</span><span class="sxs-lookup"><span data-stu-id="5914a-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="5914a-113">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="5914a-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="5914a-114">Возвращает текущий адрес памяти объекта, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="5914a-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="5914a-115">Метод IsNull</span><span class="sxs-lookup"><span data-stu-id="5914a-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="5914a-116">Возвращает значение, указывающее, является ли `ICorDebugReferenceValue` значением NULL, в этом случае `ICorDebugReferenceValue` не указывает на объект.</span><span class="sxs-lookup"><span data-stu-id="5914a-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="5914a-117">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="5914a-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="5914a-118">Задает текущий адрес памяти.</span><span class="sxs-lookup"><span data-stu-id="5914a-118">Sets the current memory address.</span></span> <span data-ttu-id="5914a-119">Это значит, что этот метод задает `ICorDebugReferenceValue`, указывающий на объект.</span><span class="sxs-lookup"><span data-stu-id="5914a-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5914a-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="5914a-120">Remarks</span></span>  
 <span data-ttu-id="5914a-121">Среда CLR может выполнять сборку мусора для объектов при продолжении отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="5914a-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="5914a-122">Сборка мусора может перемещать объекты в памяти.</span><span class="sxs-lookup"><span data-stu-id="5914a-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="5914a-123">`ICorDebugReferenceValue` будет взаимодействовать со сборкой мусора, чтобы ее сведения обновлялись после сборки мусора, или она будет неявной недействительной до сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="5914a-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="5914a-124">После продолжения отлаживаемого процесса объект `ICorDebugReferenceValue` может быть неявно недействительным.</span><span class="sxs-lookup"><span data-stu-id="5914a-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="5914a-125">Производный "ICorDebugHandleValue" не является недействительным до тех пор, пока он не будет явно освобожден или открыт.</span><span class="sxs-lookup"><span data-stu-id="5914a-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5914a-126">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="5914a-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5914a-127">Требования</span><span class="sxs-lookup"><span data-stu-id="5914a-127">Requirements</span></span>  
 <span data-ttu-id="5914a-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5914a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5914a-129">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5914a-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5914a-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5914a-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5914a-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5914a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5914a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="5914a-132">See also</span></span>

- [<span data-ttu-id="5914a-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5914a-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
