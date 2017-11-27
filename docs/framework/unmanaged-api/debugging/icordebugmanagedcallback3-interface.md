---
title: "Интерфейс ICorDebugManagedCallback3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback3
helpviewer_keywords: ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2f24cc8fbd8533ef6717bc1dcd1baab0ea9ab45
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="265ff-102">Интерфейс ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="265ff-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="265ff-103">Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="265ff-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="265ff-104">Методы</span><span class="sxs-lookup"><span data-stu-id="265ff-104">Methods</span></span>  
  
|<span data-ttu-id="265ff-105">Метод</span><span class="sxs-lookup"><span data-stu-id="265ff-105">Method</span></span>|<span data-ttu-id="265ff-106">Описание</span><span class="sxs-lookup"><span data-stu-id="265ff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="265ff-107">Метод CustomNotification</span><span class="sxs-lookup"><span data-stu-id="265ff-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="265ff-108">Указывает, что включенное пользовательское уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="265ff-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="265ff-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="265ff-109">Remarks</span></span>  
 <span data-ttu-id="265ff-110">Этот интерфейс является логическим расширением интерфейса [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) и [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="265ff-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="265ff-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="265ff-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="265ff-112">Требования</span><span class="sxs-lookup"><span data-stu-id="265ff-112">Requirements</span></span>  
 <span data-ttu-id="265ff-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="265ff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="265ff-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="265ff-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="265ff-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="265ff-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="265ff-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="265ff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265ff-117">См. также</span><span class="sxs-lookup"><span data-stu-id="265ff-117">See Also</span></span>  
 [<span data-ttu-id="265ff-118">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="265ff-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 [<span data-ttu-id="265ff-119">ICorDebugManagedCallback2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="265ff-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="265ff-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="265ff-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="265ff-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="265ff-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
