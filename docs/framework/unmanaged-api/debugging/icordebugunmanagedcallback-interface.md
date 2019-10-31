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
ms.openlocfilehash: 6de440d10f02f177e62ca3d2bd29fd5e98ea9388
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137135"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="6f523-102">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="6f523-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="6f523-103">Предоставляет уведомления о событиях машинного кода, которые не связаны напрямую с общеязыковой средой выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="6f523-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f523-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6f523-104">Methods</span></span>  
  
|<span data-ttu-id="6f523-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6f523-105">Method</span></span>|<span data-ttu-id="6f523-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6f523-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f523-107">Метод DebugEvent</span><span class="sxs-lookup"><span data-stu-id="6f523-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="6f523-108">Уведомляет отладчик о срабатывании собственного события.</span><span class="sxs-lookup"><span data-stu-id="6f523-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f523-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="6f523-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f523-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="6f523-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f523-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6f523-111">Requirements</span></span>  
 <span data-ttu-id="6f523-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f523-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f523-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f523-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f523-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f523-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f523-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f523-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f523-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6f523-116">See also</span></span>

- [<span data-ttu-id="6f523-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6f523-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
