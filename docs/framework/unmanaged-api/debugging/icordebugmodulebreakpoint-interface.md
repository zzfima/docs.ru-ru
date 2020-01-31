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
ms.openlocfilehash: df3ad3fa4ef4eeee7e23ca1629da7a8b8ce09711
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792927"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="b476e-102">Интерфейс ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="b476e-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="b476e-103">Предоставляет доступ к конкретным модулям.</span><span class="sxs-lookup"><span data-stu-id="b476e-103">Provides access to specific modules.</span></span> <span data-ttu-id="b476e-104">Этот интерфейс является подклассом интерфейса Икордебугбреакпоинт.</span><span class="sxs-lookup"><span data-stu-id="b476e-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b476e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b476e-105">Methods</span></span>  
  
|<span data-ttu-id="b476e-106">Метод</span><span class="sxs-lookup"><span data-stu-id="b476e-106">Method</span></span>|<span data-ttu-id="b476e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b476e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b476e-108">Метод GetModule</span><span class="sxs-lookup"><span data-stu-id="b476e-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="b476e-109">Возвращает указатель интерфейса на объект ICorDebugModule, который ссылается на модуль, в котором задана эта точка останова.</span><span class="sxs-lookup"><span data-stu-id="b476e-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b476e-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="b476e-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b476e-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="b476e-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b476e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b476e-112">Requirements</span></span>  
 <span data-ttu-id="b476e-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b476e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b476e-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b476e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b476e-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b476e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b476e-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b476e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b476e-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="b476e-117">See also</span></span>

- [<span data-ttu-id="b476e-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b476e-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
