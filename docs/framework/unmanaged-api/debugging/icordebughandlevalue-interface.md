---
title: Интерфейс ICorDebugHandleValue
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3219554cf953b8de31e236b2f484478172673f7b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915009"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="bc675-102">Интерфейс ICorDebugHandleValue</span><span class="sxs-lookup"><span data-stu-id="bc675-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="bc675-103">Подкласс ICorDebugReferenceValue, представляющий ссылочное значение, в котором отладчик создал маркер для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bc675-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc675-104">Методы</span><span class="sxs-lookup"><span data-stu-id="bc675-104">Methods</span></span>  
  
|<span data-ttu-id="bc675-105">Метод</span><span class="sxs-lookup"><span data-stu-id="bc675-105">Method</span></span>|<span data-ttu-id="bc675-106">Описание</span><span class="sxs-lookup"><span data-stu-id="bc675-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc675-107">Метод Dispose</span><span class="sxs-lookup"><span data-stu-id="bc675-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="bc675-108">Освобождает дескриптор, на который ссылается `ICorDebugHandleValue` этот объект, без явного освобождения указателя интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bc675-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="bc675-109">Метод GetHandleType</span><span class="sxs-lookup"><span data-stu-id="bc675-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="bc675-110">Возвращает значение Кордебугхандлетипе, описывающее тип маркера, на который ссылается `ICorDebugHandleValue`this.</span><span class="sxs-lookup"><span data-stu-id="bc675-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc675-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc675-111">Remarks</span></span>  
 <span data-ttu-id="bc675-112">`ICorDebugReferenceValue` Объект становится недействительным при прерывании выполнения отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="bc675-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="bc675-113">`ICorDebugHandleValue` Сохраняет ссылку на разрывы и продолжения до тех пор, пока он не будет явно освобожден.</span><span class="sxs-lookup"><span data-stu-id="bc675-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc675-114">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="bc675-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc675-115">Требования</span><span class="sxs-lookup"><span data-stu-id="bc675-115">Requirements</span></span>  
 <span data-ttu-id="bc675-116">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc675-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc675-117">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="bc675-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc675-118">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="bc675-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc675-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc675-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc675-120">См. также</span><span class="sxs-lookup"><span data-stu-id="bc675-120">See also</span></span>

- [<span data-ttu-id="bc675-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bc675-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
