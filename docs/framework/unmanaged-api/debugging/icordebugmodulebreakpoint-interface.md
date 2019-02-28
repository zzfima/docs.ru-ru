---
title: Интерфейс ICorDebugModuleBreakpoint
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3916bf8f7792e82ba905554bb32696f81634f819
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971524"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="f66b7-102">Интерфейс ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f66b7-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="f66b7-103">Предоставляет доступ к конкретным модулям.</span><span class="sxs-lookup"><span data-stu-id="f66b7-103">Provides access to specific modules.</span></span> <span data-ttu-id="f66b7-104">Этот интерфейс является подклассом ICorDebugBreakpoint-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f66b7-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f66b7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f66b7-105">Methods</span></span>  
  
|<span data-ttu-id="f66b7-106">Метод</span><span class="sxs-lookup"><span data-stu-id="f66b7-106">Method</span></span>|<span data-ttu-id="f66b7-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="f66b7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f66b7-108">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="f66b7-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="f66b7-109">Получает указатель на интерфейс ICorDebugModule, ссылается на модуль, устанавливаемый данной точки останова.</span><span class="sxs-lookup"><span data-stu-id="f66b7-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f66b7-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f66b7-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f66b7-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f66b7-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f66b7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f66b7-112">Requirements</span></span>  
 <span data-ttu-id="f66b7-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f66b7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f66b7-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f66b7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f66b7-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f66b7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f66b7-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f66b7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f66b7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f66b7-117">See also</span></span>
- [<span data-ttu-id="f66b7-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f66b7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
