---
title: "ICorDebugProcess2 интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2
helpviewer_keywords: ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca1a73874f6ca2f839639cbaf731a59721b2aede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2-interface1"></a><span data-ttu-id="a7bdf-102">ICorDebugProcess2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="a7bdf-102">ICorDebugProcess2 Interface1</span></span>
<span data-ttu-id="a7bdf-103">Логическое расширение интерфейса ICorDebugProcess-интерфейс, который представляет процесс выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7bdf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a7bdf-104">Methods</span></span>  
  
|<span data-ttu-id="a7bdf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a7bdf-105">Method</span></span>|<span data-ttu-id="a7bdf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a7bdf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7bdf-107">Метод ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a7bdf-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="a7bdf-108">Удаляет точку останова с указанным смещением, заданные с предыдущими вызовами метода `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="a7bdf-109">Метод GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="a7bdf-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="a7bdf-110">Получает флаги, которые должны быть заданы для общеязыковой среды выполнения (CLR) для загрузки изображения в процесс, который ссылается этот `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="a7bdf-111">Метод GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="a7bdf-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="a7bdf-112">Получает указатель ссылки на указанный управляемый объект, с дескриптором сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="a7bdf-113">Метод GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="a7bdf-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="a7bdf-114">Получает поток, на котором выполняется задача с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="a7bdf-115">GetVersion-метод</span><span class="sxs-lookup"><span data-stu-id="a7bdf-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="a7bdf-116">Возвращает версию среды CLR, на котором работает отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="a7bdf-117">Метод SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="a7bdf-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="a7bdf-118">Задает флаги, которые требуются для компилятора just-in-time (JIT) для загрузки изображения в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="a7bdf-119">Метод SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a7bdf-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="a7bdf-120">Задает неуправляемую точку останова с позиции указанного образа в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7bdf-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7bdf-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7bdf-122">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a7bdf-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7bdf-123">Требования</span><span class="sxs-lookup"><span data-stu-id="a7bdf-123">Requirements</span></span>  
 <span data-ttu-id="a7bdf-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7bdf-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7bdf-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7bdf-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7bdf-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7bdf-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7bdf-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7bdf-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7bdf-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a7bdf-128">See Also</span></span>  
 [<span data-ttu-id="a7bdf-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a7bdf-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
