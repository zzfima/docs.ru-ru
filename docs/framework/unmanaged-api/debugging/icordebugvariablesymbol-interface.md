---
title: "Интерфейс ICorDebugVariableSymbol"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a09fab1468435212c4437c58c113691e049b1ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="f78b1-102">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="f78b1-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="f78b1-103">Извлекает сведения отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="f78b1-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f78b1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f78b1-104">Methods</span></span>  
  
|<span data-ttu-id="f78b1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f78b1-105">Method</span></span>|<span data-ttu-id="f78b1-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="f78b1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f78b1-107">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="f78b1-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="f78b1-108">Получает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="f78b1-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="f78b1-109">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="f78b1-109">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="f78b1-110">Получает размер переменной в байтах.</span><span class="sxs-lookup"><span data-stu-id="f78b1-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="f78b1-111">Метод GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="f78b1-111">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="f78b1-112">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="f78b1-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="f78b1-113">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="f78b1-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="f78b1-114">Возвращает значение переменной в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="f78b1-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="f78b1-115">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="f78b1-115">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="f78b1-116">Присваивает переменной значение массива байтов.</span><span class="sxs-lookup"><span data-stu-id="f78b1-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f78b1-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="f78b1-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f78b1-118">Этот интерфейс доступен только в  .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f78b1-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f78b1-119">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f78b1-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f78b1-120">Требования</span><span class="sxs-lookup"><span data-stu-id="f78b1-120">Requirements</span></span>  
 <span data-ttu-id="f78b1-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f78b1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f78b1-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f78b1-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f78b1-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f78b1-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f78b1-124">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f78b1-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f78b1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f78b1-125">See Also</span></span>  
 [<span data-ttu-id="f78b1-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f78b1-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f78b1-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="f78b1-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
