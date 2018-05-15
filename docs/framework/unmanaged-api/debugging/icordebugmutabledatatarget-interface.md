---
title: Интерфейс ICorDebugMutableDataTarget
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 677db647320ff4014b791502b7ac1b261378c8dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmutabledatatarget-interface"></a><span data-ttu-id="08d2d-102">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="08d2d-102">ICorDebugMutableDataTarget Interface</span></span>
<span data-ttu-id="08d2d-103">Расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс для поддержки целевых объектов изменяемых данных.</span><span class="sxs-lookup"><span data-stu-id="08d2d-103">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08d2d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="08d2d-104">Methods</span></span>  
  
|<span data-ttu-id="08d2d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="08d2d-105">Method</span></span>|<span data-ttu-id="08d2d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="08d2d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08d2d-107">Метод ContinueStatusChanged</span><span class="sxs-lookup"><span data-stu-id="08d2d-107">ContinueStatusChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|<span data-ttu-id="08d2d-108">Изменяет состояние продолжения для незавершенных событий отладки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="08d2d-108">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>|  
|[<span data-ttu-id="08d2d-109">Метод SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="08d2d-109">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|<span data-ttu-id="08d2d-110">Задает контекст (значения регистра) для потока.</span><span class="sxs-lookup"><span data-stu-id="08d2d-110">Sets the context (register values) for a thread.</span></span>|  
|[<span data-ttu-id="08d2d-111">Метод WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="08d2d-111">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|<span data-ttu-id="08d2d-112">Записывает память в адресное пространство целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="08d2d-112">Writes memory into the target process address space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08d2d-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="08d2d-113">Remarks</span></span>  
 <span data-ttu-id="08d2d-114">Это расширение для [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс может быть реализовано средствами отладки, чтобы изменить целевой процесс (например, чтобы выполнить динамическую инвазивную отладку).</span><span class="sxs-lookup"><span data-stu-id="08d2d-114">This extension to the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface can be implemented by debugging tools that wish to modify the target process (for example, to perform live invasive debugging).</span></span>  
  
 <span data-ttu-id="08d2d-115">Все эти методы являются необязательными в том смысле, что никакая функциональность отладки на основе проверки ядра не будет потеряна, если этот интерфейс не будет реализован или если произойдет сбой вызова этих методов.</span><span class="sxs-lookup"><span data-stu-id="08d2d-115">All of these methods are optional in the sense that no core inspection-based debugging functionality is lost by not implementing this interface or by the failure of calls to these methods.</span></span>  <span data-ttu-id="08d2d-116">Любое свидетельствующее об ошибке значение `HRESULT` из этих методов будет исключаться, как и значение `HRESULT` из вызова метода ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="08d2d-116">Any failure `HRESULT` from these methods will propagate out as the `HRESULT` from the ICorDebug method call.</span></span>  
  
 <span data-ttu-id="08d2d-117">Обратите внимание, что единственный вызов метода ICorDebug может привести к нескольким изменениям, и механизм гарантированного применения соответствующих изменений в транзакции (все или ничего) не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="08d2d-117">Note that a single ICorDebug method call may result in multiple mutations, and that there is no mechanism for ensuring related mutations are applied transactionally (all-or-none).</span></span>  <span data-ttu-id="08d2d-118">Это означает, что в случае сбоя изменения после успешного применения других изменений (для того же вызова ICorDebug) целевой процесс может остаться в несогласованном состоянии, и отладка может оказаться ненадежной.</span><span class="sxs-lookup"><span data-stu-id="08d2d-118">This means that if a mutation fails after others (for the same ICorDebug call) have succeeded, the target process may be left in an inconsistent state and debugging may become unreliable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08d2d-119">Требования</span><span class="sxs-lookup"><span data-stu-id="08d2d-119">Requirements</span></span>  
 <span data-ttu-id="08d2d-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08d2d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08d2d-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08d2d-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08d2d-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08d2d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08d2d-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08d2d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08d2d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="08d2d-124">See Also</span></span>  
 [<span data-ttu-id="08d2d-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="08d2d-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="08d2d-126">Отладка</span><span class="sxs-lookup"><span data-stu-id="08d2d-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
