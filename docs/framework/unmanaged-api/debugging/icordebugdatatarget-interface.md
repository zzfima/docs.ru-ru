---
title: Интерфейс ICorDebugDataTarget
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c6a8ee1bcc65e640ef871e57acdeef21acd7896
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930823"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="f929d-102">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="f929d-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="f929d-103">Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.</span><span class="sxs-lookup"><span data-stu-id="f929d-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f929d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f929d-104">Methods</span></span>  
  
|<span data-ttu-id="f929d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f929d-105">Method</span></span>|<span data-ttu-id="f929d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f929d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f929d-107">Метод GetPlatform</span><span class="sxs-lookup"><span data-stu-id="f929d-107">GetPlatform Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="f929d-108">Предоставляет сведения о платформе, включая архитектуру процессора и операционную систему, на которых выполняется целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="f929d-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="f929d-109">Метод ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="f929d-109">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="f929d-110">Возвращает блок непрерывной памяти, начиная с указанного адреса, и возвращает его в указанном буфере.</span><span class="sxs-lookup"><span data-stu-id="f929d-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="f929d-111">Метод GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="f929d-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="f929d-112">Запрашивает текущий контекст потока для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="f929d-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f929d-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="f929d-113">Remarks</span></span>  
 <span data-ttu-id="f929d-114">`ICorDebugDataTarget`и его методы имеют следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="f929d-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
- <span data-ttu-id="f929d-115">Службы отладки вызывают методы этого интерфейса для доступа к памяти и другим данным в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="f929d-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
- <span data-ttu-id="f929d-116">Клиент отладчика должен реализовать этот интерфейс в соответствии с конкретным целевым объектом (например, в реальном процессе или дампе памяти).</span><span class="sxs-lookup"><span data-stu-id="f929d-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
- <span data-ttu-id="f929d-117">Методы могут вызываться только в методах, реализованных в других `ICorDebug*` интерфейсах. `ICorDebugDataTarget`</span><span class="sxs-lookup"><span data-stu-id="f929d-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="f929d-118">Это гарантирует, что клиент отладчика будет контролировать, в каком потоке он вызывается, и когда.</span><span class="sxs-lookup"><span data-stu-id="f929d-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
- <span data-ttu-id="f929d-119">`ICorDebugDataTarget` Реализация всегда должна возвращать актуальные сведения о целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="f929d-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="f929d-120">Целевой процесс должен быть остановлен и не изменяется каким-либо образом при `ICorDebug*` вызове интерфейсов `ICorDebugDataTarget` (и, следовательно, методов).</span><span class="sxs-lookup"><span data-stu-id="f929d-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="f929d-121">Если целевой объект является динамическим процессом и изменяется его состояние, метод [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) необходимо вызвать снова, чтобы предоставить экземпляр ICorDebugProcess для замены.</span><span class="sxs-lookup"><span data-stu-id="f929d-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f929d-122">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f929d-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f929d-123">Требования</span><span class="sxs-lookup"><span data-stu-id="f929d-123">Requirements</span></span>  
 <span data-ttu-id="f929d-124">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f929d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f929d-125">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f929d-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f929d-126">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="f929d-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f929d-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f929d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f929d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f929d-128">See also</span></span>

- [<span data-ttu-id="f929d-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f929d-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f929d-130">Отладка</span><span class="sxs-lookup"><span data-stu-id="f929d-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
