---
title: Интерфейс ICorDebugVariableHomeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e67e4685320f56a4a6a8be2e3eb2e6c8065ce59
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080388"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="c6481-102">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="c6481-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="c6481-103">Предоставляет перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="c6481-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6481-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c6481-104">Methods</span></span>  
  
|<span data-ttu-id="c6481-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c6481-105">Method</span></span>|<span data-ttu-id="c6481-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c6481-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6481-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="c6481-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="c6481-108">Возвращает заданное число [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляров, которые содержат сведения о локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="c6481-108">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6481-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6481-109">Remarks</span></span>  
 <span data-ttu-id="c6481-110">`ICorDebugVariableHomeEnum` Интерфейс реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="c6481-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="c6481-111">`ICorDebugVariableHomeEnum` Экземпляр заполняется [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляров путем вызова [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="c6481-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="c6481-112">Каждый [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляра в коллекции представляет локальную переменную или аргумент в функции.</span><span class="sxs-lookup"><span data-stu-id="c6481-112">Each [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="c6481-113">[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) объектов в коллекции можно перечислить, вызвав [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="c6481-113">The  [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6481-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c6481-114">Requirements</span></span>  
 <span data-ttu-id="c6481-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6481-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6481-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6481-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6481-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6481-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c6481-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c6481-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c6481-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c6481-119">See also</span></span>

- [<span data-ttu-id="c6481-120">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="c6481-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="c6481-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c6481-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
