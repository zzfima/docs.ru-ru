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
ms.openlocfilehash: 89bae73e9dfb729e26f54dc7874418163870dc27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="2ddab-102">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="2ddab-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="2ddab-103">Извлекает сведения отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="2ddab-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ddab-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2ddab-104">Methods</span></span>  
  
|<span data-ttu-id="2ddab-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2ddab-105">Method</span></span>|<span data-ttu-id="2ddab-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2ddab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ddab-107">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="2ddab-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="2ddab-108">Получает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="2ddab-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="2ddab-109">GetSize-метод</span><span class="sxs-lookup"><span data-stu-id="2ddab-109">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="2ddab-110">Получает размер переменной в байтах.</span><span class="sxs-lookup"><span data-stu-id="2ddab-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="2ddab-111">Метод GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="2ddab-111">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="2ddab-112">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="2ddab-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="2ddab-113">GetValue-метод</span><span class="sxs-lookup"><span data-stu-id="2ddab-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="2ddab-114">Возвращает значение переменной в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="2ddab-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="2ddab-115">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="2ddab-115">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="2ddab-116">Присваивает переменной значение массива байтов.</span><span class="sxs-lookup"><span data-stu-id="2ddab-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ddab-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ddab-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ddab-118">Этот интерфейс доступен только в  .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2ddab-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="2ddab-119">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2ddab-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ddab-120">Требования</span><span class="sxs-lookup"><span data-stu-id="2ddab-120">Requirements</span></span>  
 <span data-ttu-id="2ddab-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ddab-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ddab-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ddab-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ddab-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ddab-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ddab-124">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ddab-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ddab-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2ddab-125">See Also</span></span>  
 [<span data-ttu-id="2ddab-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2ddab-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="2ddab-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="2ddab-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
