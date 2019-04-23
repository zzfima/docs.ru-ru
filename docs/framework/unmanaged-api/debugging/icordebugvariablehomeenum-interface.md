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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080388"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="77899-102">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="77899-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="77899-103">Предоставляет перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="77899-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="77899-104">Методы</span><span class="sxs-lookup"><span data-stu-id="77899-104">Methods</span></span>  
  
|<span data-ttu-id="77899-105">Метод</span><span class="sxs-lookup"><span data-stu-id="77899-105">Method</span></span>|<span data-ttu-id="77899-106">Описание</span><span class="sxs-lookup"><span data-stu-id="77899-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="77899-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="77899-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="77899-108">Возвращает заданное число [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляров, которые содержат сведения о локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="77899-108">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77899-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="77899-109">Remarks</span></span>  
 <span data-ttu-id="77899-110">`ICorDebugVariableHomeEnum` Интерфейс реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="77899-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="77899-111">`ICorDebugVariableHomeEnum` Экземпляр заполняется [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляров путем вызова [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="77899-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="77899-112">Каждый [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляра в коллекции представляет локальную переменную или аргумент в функции.</span><span class="sxs-lookup"><span data-stu-id="77899-112">Each [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="77899-113">[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) объектов в коллекции можно перечислить, вызвав [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="77899-113">The  [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77899-114">Требования</span><span class="sxs-lookup"><span data-stu-id="77899-114">Requirements</span></span>  
 <span data-ttu-id="77899-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77899-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77899-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77899-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77899-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77899-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77899-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77899-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77899-119">См. также</span><span class="sxs-lookup"><span data-stu-id="77899-119">See also</span></span>

- [<span data-ttu-id="77899-120">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="77899-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="77899-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="77899-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
