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
ms.openlocfilehash: 94472e84b73cdffe09505088b1e7fbc20a209bc3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138484"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="4c4c0-102">Интерфейс ICorDebugHandleValue</span><span class="sxs-lookup"><span data-stu-id="4c4c0-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="4c4c0-103">Подкласс ICorDebugReferenceValue, представляющий ссылочное значение, в котором отладчик создал маркер для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4c4c0-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c4c0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4c4c0-104">Methods</span></span>  
  
|<span data-ttu-id="4c4c0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4c4c0-105">Method</span></span>|<span data-ttu-id="4c4c0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4c4c0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c4c0-107">Метод Dispose</span><span class="sxs-lookup"><span data-stu-id="4c4c0-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="4c4c0-108">Освобождает дескриптор, на который ссылается данный объект `ICorDebugHandleValue`, без явного освобождения указателя интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4c4c0-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="4c4c0-109">Метод GetHandleType</span><span class="sxs-lookup"><span data-stu-id="4c4c0-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="4c4c0-110">Возвращает значение Кордебугхандлетипе, описывающее тип маркера, на который ссылается этот `ICorDebugHandleValue`.</span><span class="sxs-lookup"><span data-stu-id="4c4c0-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c4c0-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="4c4c0-111">Remarks</span></span>  
 <span data-ttu-id="4c4c0-112">Объект `ICorDebugReferenceValue` становится недействительным при прерывании выполнения отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="4c4c0-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="4c4c0-113">`ICorDebugHandleValue` сохраняет свои ссылки с помощью разрывов и продолжений, пока он не будет явно освобожден.</span><span class="sxs-lookup"><span data-stu-id="4c4c0-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c4c0-114">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="4c4c0-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c4c0-115">Требования</span><span class="sxs-lookup"><span data-stu-id="4c4c0-115">Requirements</span></span>  
 <span data-ttu-id="4c4c0-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c4c0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c4c0-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c4c0-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c4c0-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c4c0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c4c0-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c4c0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c4c0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4c4c0-120">See also</span></span>

- [<span data-ttu-id="4c4c0-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4c4c0-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
