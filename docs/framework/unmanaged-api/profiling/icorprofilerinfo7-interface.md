---
title: "Интерфейс ICorProfilerInfo7"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a85bf82a01f431e42a5714eeb54e17a34314534
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="8244d-102">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="8244d-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="8244d-103">[Поддерживается в [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="8244d-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="8244d-104">Подкласс [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , предоставляет метод для применения вновь определен метаданных для модуля и, обеспечивающий доступ к поток символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="8244d-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8244d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8244d-105">Methods</span></span>  
  
|<span data-ttu-id="8244d-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8244d-106">Method</span></span>|<span data-ttu-id="8244d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8244d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8244d-108">Метод ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="8244d-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="8244d-109">Применяет метаданные, определяемые вновь `IMetadataEmit::Define*` методы для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="8244d-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="8244d-110">Метод GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="8244d-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="8244d-111">Возвращает длину потока в памяти символа.</span><span class="sxs-lookup"><span data-stu-id="8244d-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="8244d-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="8244d-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="8244d-113">Считывает байт из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="8244d-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8244d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8244d-114">Requirements</span></span>  
 <span data-ttu-id="8244d-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8244d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8244d-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8244d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8244d-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8244d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8244d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8244d-118">See Also</span></span>  
 [<span data-ttu-id="8244d-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="8244d-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
