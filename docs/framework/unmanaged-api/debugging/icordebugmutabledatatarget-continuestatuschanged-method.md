---
title: "Метод ICorDebugMutableDataTarget::ContinueStatusChanged"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2f4f3890f2cfb2e3b017b8c7d0705d8c8e063957
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="4af9a-102">Метод ICorDebugMutableDataTarget::ContinueStatusChanged</span><span class="sxs-lookup"><span data-stu-id="4af9a-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>
<span data-ttu-id="4af9a-103">Изменяет состояние продолжения для незавершенных событий отладки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="4af9a-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4af9a-104">Syntax</span></span>  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4af9a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4af9a-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="4af9a-106">Идентификатор потока, определяемый операционной системой.</span><span class="sxs-lookup"><span data-stu-id="4af9a-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="4af9a-107">Объект[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)значение, которое представляет новое запрошенное состояние продолжения.</span><span class="sxs-lookup"><span data-stu-id="4af9a-107">A[COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4af9a-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4af9a-108">Remarks</span></span>  
 <span data-ttu-id="4af9a-109">Отладчик вызывает метод `ContinueStatusChanged` при вызове метода ICorDebug, требующего, чтобы способ обработки текущего события отладки потенциально отличался от способа, которым оно обычно обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="4af9a-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="4af9a-110">Например, если имеется незавершенное исключение и отладчик запрашивает операцию, которая будет отменять это исключение (например, [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) или `FuncEval`), этот API используется для запроса, быть исключение отменено.</span><span class="sxs-lookup"><span data-stu-id="4af9a-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4af9a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4af9a-111">Requirements</span></span>  
 <span data-ttu-id="4af9a-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4af9a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4af9a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4af9a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4af9a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4af9a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4af9a-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4af9a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af9a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4af9a-116">See Also</span></span>  
 [<span data-ttu-id="4af9a-117">Интерфейс ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="4af9a-117">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="4af9a-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4af9a-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
