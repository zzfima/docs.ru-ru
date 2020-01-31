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
ms.openlocfilehash: 74b3c7bed54f3735efbd5d2c56962d427518f71a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790947"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="c41ff-102">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="c41ff-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="c41ff-103">Предоставляет перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="c41ff-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c41ff-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c41ff-104">Methods</span></span>  
  
|<span data-ttu-id="c41ff-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c41ff-105">Method</span></span>|<span data-ttu-id="c41ff-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c41ff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c41ff-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="c41ff-107">Next Method</span></span>](icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="c41ff-108">Возвращает указанное число экземпляров [ICorDebugVariableHome](icordebugvariablehome-interface.md) , содержащих сведения о локальных переменных и аргументах в функции.</span><span class="sxs-lookup"><span data-stu-id="c41ff-108">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c41ff-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="c41ff-109">Remarks</span></span>  
 <span data-ttu-id="c41ff-110">Интерфейс `ICorDebugVariableHomeEnum` реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="c41ff-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="c41ff-111">Экземпляр `ICorDebugVariableHomeEnum` заполняется экземплярами [ICorDebugVariableHome](icordebugvariablehome-interface.md) путем вызова метода [ICorDebugCode4:: енумератевариаблехомес](icordebugcode4-enumeratevariablehomes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c41ff-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="c41ff-112">Каждый экземпляр [ICorDebugVariableHome](icordebugvariablehome-interface.md) в коллекции представляет локальную переменную или аргумент в функции.</span><span class="sxs-lookup"><span data-stu-id="c41ff-112">Each [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="c41ff-113">Объекты [ICorDebugVariableHome](icordebugvariablehome-interface.md) в коллекции можно перечислить, вызвав метод [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c41ff-113">The  [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c41ff-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c41ff-114">Requirements</span></span>  
 <span data-ttu-id="c41ff-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c41ff-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c41ff-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c41ff-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c41ff-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c41ff-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c41ff-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c41ff-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c41ff-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="c41ff-119">See also</span></span>

- [<span data-ttu-id="c41ff-120">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="c41ff-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="c41ff-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c41ff-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
