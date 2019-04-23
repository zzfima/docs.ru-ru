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
ms.openlocfilehash: d6a43a264fcaa94ce4e629d8db504e9d416f6b89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179716"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="db2c9-102">Интерфейс ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="db2c9-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="db2c9-103">Предоставляет доступ к конкретным модулям.</span><span class="sxs-lookup"><span data-stu-id="db2c9-103">Provides access to specific modules.</span></span> <span data-ttu-id="db2c9-104">Этот интерфейс является подклассом ICorDebugBreakpoint-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="db2c9-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db2c9-105">Методы</span><span class="sxs-lookup"><span data-stu-id="db2c9-105">Methods</span></span>  
  
|<span data-ttu-id="db2c9-106">Метод</span><span class="sxs-lookup"><span data-stu-id="db2c9-106">Method</span></span>|<span data-ttu-id="db2c9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="db2c9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db2c9-108">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="db2c9-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="db2c9-109">Получает указатель на интерфейс ICorDebugModule, ссылается на модуль, устанавливаемый данной точки останова.</span><span class="sxs-lookup"><span data-stu-id="db2c9-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db2c9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="db2c9-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db2c9-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="db2c9-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db2c9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="db2c9-112">Requirements</span></span>  
 <span data-ttu-id="db2c9-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db2c9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db2c9-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db2c9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db2c9-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db2c9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db2c9-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db2c9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2c9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="db2c9-117">See also</span></span>

- [<span data-ttu-id="db2c9-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="db2c9-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
