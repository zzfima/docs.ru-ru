---
title: "Интерфейс ICorDebugVariableHomeEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHomeEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHomeEnum
helpviewer_keywords: ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7e64a52ca70606f83138b636f7ccb62ba18908f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="edda5-102">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="edda5-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="edda5-103">Предоставляет перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="edda5-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="edda5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="edda5-104">Methods</span></span>  
  
|<span data-ttu-id="edda5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="edda5-105">Method</span></span>|<span data-ttu-id="edda5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="edda5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="edda5-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="edda5-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="edda5-108">Возвращает заданное число [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляров, которые содержат сведения о локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="edda5-108">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edda5-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="edda5-109">Remarks</span></span>  
 <span data-ttu-id="edda5-110">`ICorDebugVariableHomeEnum` ICorDebugEnum-интерфейс реализует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="edda5-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="edda5-111">`ICorDebugVariableHomeEnum` Заполненный экземпляр [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляры путем вызова [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="edda5-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="edda5-112">Каждый [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляра в коллекции представляет локальную переменную или аргумент в функции.</span><span class="sxs-lookup"><span data-stu-id="edda5-112">Each [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="edda5-113">[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) объектов в коллекции могут быть перечислены путем вызова [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="edda5-113">The  [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edda5-114">Требования</span><span class="sxs-lookup"><span data-stu-id="edda5-114">Requirements</span></span>  
 <span data-ttu-id="edda5-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edda5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edda5-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="edda5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="edda5-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edda5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edda5-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edda5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edda5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="edda5-119">See Also</span></span>  
 [<span data-ttu-id="edda5-120">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="edda5-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 [<span data-ttu-id="edda5-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="edda5-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
