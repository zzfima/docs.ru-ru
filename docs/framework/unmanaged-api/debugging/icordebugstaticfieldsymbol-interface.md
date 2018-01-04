---
title: "Интерфейс ICorDebugStaticFieldSymbol"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a25e19bf43d852670bc5f4f491fb25707395e04a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="65a6b-102">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="65a6b-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="65a6b-103">Представляет сведения отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="65a6b-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65a6b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="65a6b-104">Methods</span></span>  
  
|<span data-ttu-id="65a6b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="65a6b-105">Method</span></span>|<span data-ttu-id="65a6b-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="65a6b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65a6b-107">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="65a6b-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="65a6b-108">Получает адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="65a6b-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="65a6b-109">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="65a6b-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="65a6b-110">Получает имя статического поля.</span><span class="sxs-lookup"><span data-stu-id="65a6b-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="65a6b-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="65a6b-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="65a6b-112">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="65a6b-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65a6b-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="65a6b-113">Remarks</span></span>  
 <span data-ttu-id="65a6b-114">Интерфейс `ICorDebugStaticFieldSymbol` используется для извлечения сведений символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="65a6b-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65a6b-115">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="65a6b-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="65a6b-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="65a6b-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65a6b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="65a6b-117">Requirements</span></span>  
 <span data-ttu-id="65a6b-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65a6b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65a6b-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65a6b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65a6b-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65a6b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65a6b-121">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65a6b-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a6b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="65a6b-122">See Also</span></span>  
 [<span data-ttu-id="65a6b-123">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="65a6b-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="65a6b-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="65a6b-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="65a6b-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="65a6b-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
