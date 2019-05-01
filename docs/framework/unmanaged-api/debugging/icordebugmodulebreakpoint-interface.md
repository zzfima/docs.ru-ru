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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994738"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="ad7c6-102">Интерфейс ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ad7c6-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="ad7c6-103">Предоставляет доступ к конкретным модулям.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-103">Provides access to specific modules.</span></span> <span data-ttu-id="ad7c6-104">Этот интерфейс является подклассом ICorDebugBreakpoint-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad7c6-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ad7c6-105">Methods</span></span>  
  
|<span data-ttu-id="ad7c6-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ad7c6-106">Method</span></span>|<span data-ttu-id="ad7c6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ad7c6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad7c6-108">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="ad7c6-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="ad7c6-109">Получает указатель на интерфейс ICorDebugModule, ссылается на модуль, устанавливаемый данной точки останова.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad7c6-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad7c6-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad7c6-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad7c6-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ad7c6-112">Requirements</span></span>  
 <span data-ttu-id="ad7c6-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad7c6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad7c6-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad7c6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad7c6-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad7c6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad7c6-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad7c6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad7c6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ad7c6-117">See also</span></span>

- [<span data-ttu-id="ad7c6-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ad7c6-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
