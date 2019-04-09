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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128684"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="beadd-102">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="beadd-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="beadd-103">Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно с общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="beadd-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="beadd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="beadd-104">Methods</span></span>  
  
|<span data-ttu-id="beadd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="beadd-105">Method</span></span>|<span data-ttu-id="beadd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="beadd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="beadd-107">Метод DebugEvent</span><span class="sxs-lookup"><span data-stu-id="beadd-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="beadd-108">Уведомляет отладчик о том, что произошло событие машинного кода.</span><span class="sxs-lookup"><span data-stu-id="beadd-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beadd-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="beadd-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="beadd-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="beadd-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beadd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="beadd-111">Requirements</span></span>  
 <span data-ttu-id="beadd-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beadd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beadd-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="beadd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="beadd-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beadd-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="beadd-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="beadd-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="beadd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="beadd-116">See also</span></span>

- [<span data-ttu-id="beadd-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="beadd-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
