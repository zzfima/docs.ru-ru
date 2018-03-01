---
title: "ICorDebugHandleValue интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b8df7b46bf22fa1a3a8633cbad7ad1a6582b4860
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebughandlevalue-interface1"></a><span data-ttu-id="f2ddf-102">ICorDebugHandleValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="f2ddf-102">ICorDebugHandleValue Interface1</span></span>
<span data-ttu-id="f2ddf-103">Подкласс ICorDebugReferenceValue, представляющий значение ссылки, для которого отладчик создал дескриптор сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f2ddf-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2ddf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f2ddf-104">Methods</span></span>  
  
|<span data-ttu-id="f2ddf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f2ddf-105">Method</span></span>|<span data-ttu-id="f2ddf-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="f2ddf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2ddf-107">Метод Dispose</span><span class="sxs-lookup"><span data-stu-id="f2ddf-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="f2ddf-108">Освобождает дескриптор ссылается этот `ICorDebugHandleValue` объекта без явного освобождения указатель на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f2ddf-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="f2ddf-109">Метод GetHandleType</span><span class="sxs-lookup"><span data-stu-id="f2ddf-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="f2ddf-110">Возвращает значение CorDebugHandleType, описывающее тип ссылается этот дескриптор `ICorDebugHandleValue`.</span><span class="sxs-lookup"><span data-stu-id="f2ddf-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2ddf-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2ddf-111">Remarks</span></span>  
 <span data-ttu-id="f2ddf-112">`ICorDebugReferenceValue` Объект становится недействительным перерывом в выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="f2ddf-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="f2ddf-113">`ICorDebugHandleValue` Сохраняет свою ссылку разрывы, продолжения, пока не освобождается явно.</span><span class="sxs-lookup"><span data-stu-id="f2ddf-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2ddf-114">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f2ddf-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ddf-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f2ddf-115">Requirements</span></span>  
 <span data-ttu-id="f2ddf-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2ddf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ddf-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2ddf-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2ddf-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2ddf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2ddf-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ddf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ddf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f2ddf-120">See Also</span></span>  
 [<span data-ttu-id="f2ddf-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f2ddf-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
