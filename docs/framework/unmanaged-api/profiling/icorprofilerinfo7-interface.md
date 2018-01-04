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
ms.workload: dotnet
ms.openlocfilehash: 13282bec74df5e6159148aa4fbe92a84d035e044
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="2346a-102">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="2346a-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="2346a-103">[Поддерживается в [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="2346a-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="2346a-104">Подкласс [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , предоставляет метод для применения вновь определен метаданных для модуля и, обеспечивающий доступ к поток символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="2346a-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2346a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2346a-105">Methods</span></span>  
  
|<span data-ttu-id="2346a-106">Метод</span><span class="sxs-lookup"><span data-stu-id="2346a-106">Method</span></span>|<span data-ttu-id="2346a-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="2346a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2346a-108">Метод ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="2346a-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="2346a-109">Применяет метаданные, определяемые вновь `IMetadataEmit::Define*` методы для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="2346a-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="2346a-110">Метод GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="2346a-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="2346a-111">Возвращает длину потока в памяти символа.</span><span class="sxs-lookup"><span data-stu-id="2346a-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="2346a-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="2346a-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="2346a-113">Считывает байт из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="2346a-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2346a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="2346a-114">Requirements</span></span>  
 <span data-ttu-id="2346a-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2346a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2346a-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2346a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2346a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2346a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2346a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2346a-118">See Also</span></span>  
 [<span data-ttu-id="2346a-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="2346a-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
