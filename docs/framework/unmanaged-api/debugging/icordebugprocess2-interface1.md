---
title: Интерфейс1 ICorDebugProcess2
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b37cb8ecd178b90a4dcd2d2eab9fa7c4cd3211d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647326"
---
# <a name="icordebugprocess2-interface1"></a><span data-ttu-id="2791b-102">Интерфейс1 ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="2791b-102">ICorDebugProcess2 Interface1</span></span>
<span data-ttu-id="2791b-103">Логическим расширением интерфейса ICorDebugProcess, который представляет процесс выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="2791b-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2791b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2791b-104">Methods</span></span>  
  
|<span data-ttu-id="2791b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2791b-105">Method</span></span>|<span data-ttu-id="2791b-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="2791b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2791b-107">Метод ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2791b-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="2791b-108">Удаляет точку останова с указанным смещением, установленное с предыдущими вызовами `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="2791b-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="2791b-109">Метод GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="2791b-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="2791b-110">Получает флаги, которые должны быть заданы для общеязыковой среды выполнения (CLR) для загрузки изображения в процесс, который ссылается этот `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="2791b-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="2791b-111">Метод GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="2791b-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="2791b-112">Получает указатель ссылки на указанный управляемый объект, с дескриптором сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2791b-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="2791b-113">Метод GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="2791b-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="2791b-114">Получает поток, на котором выполняется задача с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="2791b-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="2791b-115">Метод GetVersion</span><span class="sxs-lookup"><span data-stu-id="2791b-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="2791b-116">Получает версию среды CLR, на котором выполняется отлаживаемый процесс.</span><span class="sxs-lookup"><span data-stu-id="2791b-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="2791b-117">Метод SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="2791b-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="2791b-118">Задает флаги, которые требуются для компилятор just-in-time (JIT) для загрузки изображения в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="2791b-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="2791b-119">Метод SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2791b-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="2791b-120">Задает неуправляемую точку останова с указанным образов в машинном коде смещения.</span><span class="sxs-lookup"><span data-stu-id="2791b-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2791b-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="2791b-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2791b-122">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="2791b-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2791b-123">Требования</span><span class="sxs-lookup"><span data-stu-id="2791b-123">Requirements</span></span>  
 <span data-ttu-id="2791b-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2791b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2791b-125">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2791b-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2791b-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2791b-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2791b-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2791b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2791b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="2791b-128">See also</span></span>
- [<span data-ttu-id="2791b-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2791b-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
