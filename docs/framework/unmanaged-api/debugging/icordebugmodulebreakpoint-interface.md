---
title: "ICorDebugModuleBreakpoint интерфейс1"
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
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cec51a7efe17c2188f12039333dd90f557b1e724
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulebreakpoint-interface1"></a><span data-ttu-id="0ad72-102">ICorDebugModuleBreakpoint интерфейс1</span><span class="sxs-lookup"><span data-stu-id="0ad72-102">ICorDebugModuleBreakpoint Interface1</span></span>
<span data-ttu-id="0ad72-103">Предоставляет доступ к конкретным модулям.</span><span class="sxs-lookup"><span data-stu-id="0ad72-103">Provides access to specific modules.</span></span> <span data-ttu-id="0ad72-104">Этот интерфейс является подклассом ICorDebugBreakpoint-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0ad72-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ad72-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0ad72-105">Methods</span></span>  
  
|<span data-ttu-id="0ad72-106">Метод</span><span class="sxs-lookup"><span data-stu-id="0ad72-106">Method</span></span>|<span data-ttu-id="0ad72-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0ad72-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ad72-108">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="0ad72-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="0ad72-109">Получает указатель на интерфейс ICorDebugModule, которая ссылается на модуль, где установлена данная точка останова.</span><span class="sxs-lookup"><span data-stu-id="0ad72-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ad72-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ad72-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ad72-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0ad72-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad72-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0ad72-112">Requirements</span></span>  
 <span data-ttu-id="0ad72-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ad72-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad72-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ad72-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ad72-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ad72-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ad72-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad72-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad72-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0ad72-117">See Also</span></span>  
 [<span data-ttu-id="0ad72-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0ad72-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
