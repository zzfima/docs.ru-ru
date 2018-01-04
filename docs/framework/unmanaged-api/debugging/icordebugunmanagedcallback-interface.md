---
title: "Интерфейс ICorDebugUnmanagedCallback"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnmanagedCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnmanagedCallback
helpviewer_keywords: ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2a0dc561010ead94f1b2ffcd306a6067a04d7e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="e0b4e-102">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="e0b4e-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="e0b4e-103">Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно с общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="e0b4e-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0b4e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e0b4e-104">Methods</span></span>  
  
|<span data-ttu-id="e0b4e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e0b4e-105">Method</span></span>|<span data-ttu-id="e0b4e-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="e0b4e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0b4e-107">Метод DebugEvent</span><span class="sxs-lookup"><span data-stu-id="e0b4e-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="e0b4e-108">Уведомляет отладчик о том, что произошло событие машинного кода.</span><span class="sxs-lookup"><span data-stu-id="e0b4e-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0b4e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0b4e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0b4e-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="e0b4e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0b4e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e0b4e-111">Requirements</span></span>  
 <span data-ttu-id="e0b4e-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0b4e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0b4e-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0b4e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0b4e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0b4e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0b4e-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0b4e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0b4e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e0b4e-116">See Also</span></span>  
 [<span data-ttu-id="e0b4e-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e0b4e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
