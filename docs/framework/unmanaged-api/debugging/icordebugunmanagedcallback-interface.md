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
ms.openlocfilehash: 5b55b27d45ef3efea10215c8a4163b5981f9d145
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422866"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="ece25-102">Интерфейс ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="ece25-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="ece25-103">Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно с общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="ece25-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ece25-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ece25-104">Methods</span></span>  
  
|<span data-ttu-id="ece25-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ece25-105">Method</span></span>|<span data-ttu-id="ece25-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ece25-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ece25-107">Метод DebugEvent</span><span class="sxs-lookup"><span data-stu-id="ece25-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="ece25-108">Уведомляет отладчик о том, что произошло событие машинного кода.</span><span class="sxs-lookup"><span data-stu-id="ece25-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ece25-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ece25-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ece25-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ece25-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ece25-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ece25-111">Requirements</span></span>  
 <span data-ttu-id="ece25-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ece25-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ece25-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ece25-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ece25-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ece25-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ece25-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ece25-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece25-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ece25-116">See Also</span></span>  
 [<span data-ttu-id="ece25-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ece25-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
