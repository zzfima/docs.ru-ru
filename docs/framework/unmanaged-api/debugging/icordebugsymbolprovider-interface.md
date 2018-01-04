---
title: "Интерфейс ICorDebugSymbolProvider"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63823c535ad4d036dd5d539c8fe5381d350ccbe5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="296c3-102">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="296c3-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="296c3-103">Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах.</span><span class="sxs-lookup"><span data-stu-id="296c3-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="296c3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="296c3-104">Methods</span></span>  
  
|<span data-ttu-id="296c3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="296c3-105">Method</span></span>|<span data-ttu-id="296c3-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="296c3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="296c3-107">Метод GetAssemblyImageBytes</span><span class="sxs-lookup"><span data-stu-id="296c3-107">GetAssemblyImageBytes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="296c3-108">Считывает данные из объединенной сборки для указанного относительного виртуального адреса (RVA) в объединенной сборке.</span><span class="sxs-lookup"><span data-stu-id="296c3-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="296c3-109">Метод GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="296c3-109">GetAssemblyImageMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="296c3-110">Возвращает метаданные из объединенной сборки.</span><span class="sxs-lookup"><span data-stu-id="296c3-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="296c3-111">Метод GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="296c3-111">GetCodeRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="296c3-112">Получает начальный адрес метода и размер с учетом относительного виртуального адреса (RVA) в методе.</span><span class="sxs-lookup"><span data-stu-id="296c3-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="296c3-113">Метод GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="296c3-113">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="296c3-114">Получает символы поля экземпляра, которые соответствуют сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="296c3-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="296c3-115">Метод GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="296c3-115">GetMergedAssemblyRecords Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="296c3-116">Получает символьные записи для всех объединенных сборок.</span><span class="sxs-lookup"><span data-stu-id="296c3-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="296c3-117">Метод GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="296c3-117">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="296c3-118">Получает локальные символы метода для указанного относительного виртуального адреса (RVA) этого метода.</span><span class="sxs-lookup"><span data-stu-id="296c3-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="296c3-119">Метод GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="296c3-119">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="296c3-120">Получает символы параметров метода с учетом относительного виртуального адреса (RVA) этого метода.</span><span class="sxs-lookup"><span data-stu-id="296c3-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="296c3-121">Метод GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="296c3-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="296c3-122">Возвращает сведения о свойствах метода, такие как токен метаданных метода и сведения о его универсальных параметрах, для указанного относительного виртуального адреса (RVA) в этом методе.</span><span class="sxs-lookup"><span data-stu-id="296c3-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="296c3-123">Метод GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="296c3-123">GetObjectSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="296c3-124">Возвращает размер объекта для объекта на основе его сигнатуры TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="296c3-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="296c3-125">Метод GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="296c3-125">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="296c3-126">Получает символы статического поля, которые соответствуют сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="296c3-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="296c3-127">Метод GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="296c3-127">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="296c3-128">Возвращает сведения о свойствах типа, такие как число сигнатур его универсальных параметров, исходя из относительного виртуального адреса (RVA) в таблице VTable.</span><span class="sxs-lookup"><span data-stu-id="296c3-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="296c3-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="296c3-129">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="296c3-130">Этот интерфейс доступен только в  .NET Native.</span><span class="sxs-lookup"><span data-stu-id="296c3-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="296c3-131">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="296c3-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="296c3-132">Требования</span><span class="sxs-lookup"><span data-stu-id="296c3-132">Requirements</span></span>  
 <span data-ttu-id="296c3-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="296c3-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="296c3-134">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="296c3-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="296c3-135">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="296c3-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="296c3-136">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="296c3-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="296c3-137">См. также</span><span class="sxs-lookup"><span data-stu-id="296c3-137">See Also</span></span>  
 [<span data-ttu-id="296c3-138">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="296c3-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="296c3-139">Отладка</span><span class="sxs-lookup"><span data-stu-id="296c3-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
