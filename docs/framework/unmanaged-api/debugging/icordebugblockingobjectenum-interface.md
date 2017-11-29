---
title: "Интерфейс ICorDebugBlockingObjectEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBlockingObjectEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBlockingObjectEnum
helpviewer_keywords: ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b62da4047029881ddffff5faee9f06072407bfc6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="83ec5-102">Интерфейс ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="83ec5-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="83ec5-103">Предоставляет перечислитель для списка [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="83ec5-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="83ec5-104">Этот интерфейс является подклассом ICorDebugEnum-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="83ec5-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83ec5-105">Методы</span><span class="sxs-lookup"><span data-stu-id="83ec5-105">Methods</span></span>  
  
|<span data-ttu-id="83ec5-106">Метод</span><span class="sxs-lookup"><span data-stu-id="83ec5-106">Method</span></span>|<span data-ttu-id="83ec5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="83ec5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83ec5-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="83ec5-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="83ec5-109">Перечисляет список [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="83ec5-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83ec5-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="83ec5-110">Remarks</span></span>  
 <span data-ttu-id="83ec5-111">Каждая структура `CorDebugBlockingObject` представляет объект, блокирующий поток.</span><span class="sxs-lookup"><span data-stu-id="83ec5-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83ec5-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="83ec5-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83ec5-113">Требования</span><span class="sxs-lookup"><span data-stu-id="83ec5-113">Requirements</span></span>  
 <span data-ttu-id="83ec5-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83ec5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83ec5-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83ec5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83ec5-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83ec5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83ec5-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83ec5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ec5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="83ec5-118">See Also</span></span>  
 [<span data-ttu-id="83ec5-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="83ec5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="83ec5-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="83ec5-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
