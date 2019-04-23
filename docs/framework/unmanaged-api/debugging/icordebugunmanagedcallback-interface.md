---
title: Интерфейс ICorDebugUnmanagedCallback
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60a1546068ae6a8c8be1c0af1ef3c7d770c23d70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128684"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="d762f-102">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="d762f-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="d762f-103">Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно с общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="d762f-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d762f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d762f-104">Methods</span></span>  
  
|<span data-ttu-id="d762f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d762f-105">Method</span></span>|<span data-ttu-id="d762f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d762f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d762f-107">Метод DebugEvent</span><span class="sxs-lookup"><span data-stu-id="d762f-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="d762f-108">Уведомляет отладчик о том, что произошло событие машинного кода.</span><span class="sxs-lookup"><span data-stu-id="d762f-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d762f-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="d762f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d762f-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d762f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d762f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d762f-111">Requirements</span></span>  
 <span data-ttu-id="d762f-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d762f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d762f-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d762f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d762f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d762f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d762f-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d762f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d762f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d762f-116">See also</span></span>

- [<span data-ttu-id="d762f-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d762f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
