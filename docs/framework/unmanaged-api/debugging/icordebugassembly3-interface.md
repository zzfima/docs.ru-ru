---
title: "Интерфейс ICorDebugAssembly3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e581b4256da2ecc19a8b97520e0e70fef972b549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="8924b-102">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="8924b-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="8924b-103">Логически расширяет интерфейс ICorDebugAssembly для обеспечения поддержки контейнерных сборок и их вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="8924b-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8924b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8924b-104">Methods</span></span>  
  
|<span data-ttu-id="8924b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8924b-105">Method</span></span>|<span data-ttu-id="8924b-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="8924b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8924b-107">Метод EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="8924b-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="8924b-108">Получает перечислитель для сборок, содержащихся в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="8924b-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="8924b-109">Метод GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="8924b-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="8924b-110">Возвращает контейнерную сборку этого объекта `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="8924b-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8924b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="8924b-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8924b-112">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8924b-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="8924b-113">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8924b-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8924b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8924b-114">Requirements</span></span>  
 <span data-ttu-id="8924b-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8924b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8924b-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8924b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8924b-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8924b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8924b-118">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8924b-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8924b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8924b-119">See Also</span></span>  
 [<span data-ttu-id="8924b-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8924b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8924b-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="8924b-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
