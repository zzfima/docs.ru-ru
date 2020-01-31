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
ms.openlocfilehash: fdd2fee11e9353c3aa3faee2b137597e4ba47801
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791180"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="be797-102">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="be797-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="be797-103">Предоставляет уведомления о событиях машинного кода, которые не связаны напрямую с общеязыковой средой выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="be797-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be797-104">Методы</span><span class="sxs-lookup"><span data-stu-id="be797-104">Methods</span></span>  
  
|<span data-ttu-id="be797-105">Метод</span><span class="sxs-lookup"><span data-stu-id="be797-105">Method</span></span>|<span data-ttu-id="be797-106">Описание</span><span class="sxs-lookup"><span data-stu-id="be797-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be797-107">Метод DebugEvent</span><span class="sxs-lookup"><span data-stu-id="be797-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="be797-108">Уведомляет отладчик о срабатывании собственного события.</span><span class="sxs-lookup"><span data-stu-id="be797-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be797-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="be797-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be797-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="be797-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be797-111">Требования</span><span class="sxs-lookup"><span data-stu-id="be797-111">Requirements</span></span>  
 <span data-ttu-id="be797-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be797-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be797-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be797-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be797-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be797-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be797-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be797-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be797-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="be797-116">See also</span></span>

- [<span data-ttu-id="be797-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="be797-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
