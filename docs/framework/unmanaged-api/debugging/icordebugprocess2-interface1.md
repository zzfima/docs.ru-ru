---
title: Интерфейс ICorDebugProcess2
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
ms.openlocfilehash: 1ef6af11851acbe0f7e9469c9432ff09f9228608
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792510"
---
# <a name="icordebugprocess2-interface"></a><span data-ttu-id="34dd4-102">Интерфейс ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="34dd4-102">ICorDebugProcess2 Interface</span></span>
<span data-ttu-id="34dd4-103">Логическое расширение интерфейса ICorDebugProcess, представляющее процесс, выполняющий управляемый код.</span><span class="sxs-lookup"><span data-stu-id="34dd4-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34dd4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="34dd4-104">Methods</span></span>  
  
|<span data-ttu-id="34dd4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="34dd4-105">Method</span></span>|<span data-ttu-id="34dd4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="34dd4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34dd4-107">Метод ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="34dd4-107">ClearUnmanagedBreakpoint Method</span></span>](icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="34dd4-108">Удаляет точку останова с указанным смещением, которое было задано предыдущим вызовом метода `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="34dd4-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="34dd4-109">Метод GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="34dd4-109">GetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="34dd4-110">Возвращает флаги, которые должны быть установлены в среде CLR для загрузки изображения в процесс, на который ссылается этот `ICorDebugProcess2`.</span><span class="sxs-lookup"><span data-stu-id="34dd4-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="34dd4-111">Метод GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="34dd4-111">GetReferenceValueFromGCHandle Method</span></span>](icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="34dd4-112">Возвращает указатель ссылки на указанный управляемый объект, который имеет обработчик сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="34dd4-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="34dd4-113">Метод GetThreadForTaskID</span><span class="sxs-lookup"><span data-stu-id="34dd4-113">GetThreadForTaskID Method</span></span>](icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="34dd4-114">Возвращает поток, в котором выполняется задача с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="34dd4-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="34dd4-115">Метод GetVersion</span><span class="sxs-lookup"><span data-stu-id="34dd4-115">GetVersion Method</span></span>](icordebugprocess2-getversion-method.md)|<span data-ttu-id="34dd4-116">Возвращает версию среды CLR, на основе которой выполняется отлаживаемый процесс.</span><span class="sxs-lookup"><span data-stu-id="34dd4-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="34dd4-117">Метод SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="34dd4-117">SetDesiredNGENCompilerFlags Method</span></span>](icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="34dd4-118">Задает флаги, которые требуются для JIT-компилятора при загрузке изображения в отлаживаемый процесс.</span><span class="sxs-lookup"><span data-stu-id="34dd4-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="34dd4-119">Метод SetUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="34dd4-119">SetUnmanagedBreakpoint Method</span></span>](icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="34dd4-120">Задает неуправляемую точку останова в указанном смещении машинного образа.</span><span class="sxs-lookup"><span data-stu-id="34dd4-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34dd4-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="34dd4-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34dd4-122">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="34dd4-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34dd4-123">Требования</span><span class="sxs-lookup"><span data-stu-id="34dd4-123">Requirements</span></span>  
 <span data-ttu-id="34dd4-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34dd4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34dd4-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34dd4-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34dd4-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34dd4-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34dd4-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34dd4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34dd4-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="34dd4-128">See also</span></span>

- [<span data-ttu-id="34dd4-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="34dd4-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
