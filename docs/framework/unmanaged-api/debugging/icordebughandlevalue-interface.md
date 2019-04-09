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
ms.openlocfilehash: 9a9eb63e681b47f058901b0ff002015baffe6048
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117447"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="3a08d-102">Интерфейс ICorDebugHandleValue</span><span class="sxs-lookup"><span data-stu-id="3a08d-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="3a08d-103">Подкласс ICorDebugReferenceValue, представляющий значение ссылки, для которого отладчик создал дескриптор для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3a08d-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a08d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3a08d-104">Methods</span></span>  
  
|<span data-ttu-id="3a08d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3a08d-105">Method</span></span>|<span data-ttu-id="3a08d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3a08d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3a08d-107">Метод Dispose</span><span class="sxs-lookup"><span data-stu-id="3a08d-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="3a08d-108">Освобождает дескриптор, который ссылается этот `ICorDebugHandleValue` объекта без явно освобождая указатель интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3a08d-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="3a08d-109">Метод GetHandleType</span><span class="sxs-lookup"><span data-stu-id="3a08d-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="3a08d-110">Возвращает значение CorDebugHandleType, описывающее тип ссылается этот дескриптор `ICorDebugHandleValue`.</span><span class="sxs-lookup"><span data-stu-id="3a08d-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a08d-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="3a08d-111">Remarks</span></span>  
 <span data-ttu-id="3a08d-112">`ICorDebugReferenceValue` Объект становится недействительным перерывом в выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="3a08d-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="3a08d-113">`ICorDebugHandleValue` Сохраняет свою ссылку разрывов и продолжения, пока не освобождается явно.</span><span class="sxs-lookup"><span data-stu-id="3a08d-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a08d-114">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="3a08d-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a08d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="3a08d-115">Requirements</span></span>  
 <span data-ttu-id="3a08d-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a08d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a08d-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a08d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a08d-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a08d-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3a08d-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3a08d-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3a08d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="3a08d-120">See also</span></span>

- [<span data-ttu-id="3a08d-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3a08d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
