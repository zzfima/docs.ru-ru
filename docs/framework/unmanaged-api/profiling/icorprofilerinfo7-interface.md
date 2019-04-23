---
title: Интерфейс ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d8586031c5bcb0303a64b67ee601fe41b81ee3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134867"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="43107-102">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="43107-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="43107-103">[Поддерживается в [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="43107-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="43107-104">Подкласс [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , предоставляющий метод для применения вновь определен метаданных для модуля и, обеспечивающий доступ в поток символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="43107-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43107-105">Методы</span><span class="sxs-lookup"><span data-stu-id="43107-105">Methods</span></span>  
  
|<span data-ttu-id="43107-106">Метод</span><span class="sxs-lookup"><span data-stu-id="43107-106">Method</span></span>|<span data-ttu-id="43107-107">Описание</span><span class="sxs-lookup"><span data-stu-id="43107-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43107-108">Метод ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="43107-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="43107-109">Применяет метаданные, вновь определением `IMetadataEmit::Define*` методов к указанному модулю.</span><span class="sxs-lookup"><span data-stu-id="43107-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="43107-110">Метод GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="43107-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="43107-111">Возвращает длину потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="43107-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="43107-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="43107-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="43107-113">Считывает байт из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="43107-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43107-114">Требования</span><span class="sxs-lookup"><span data-stu-id="43107-114">Requirements</span></span>  
 <span data-ttu-id="43107-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43107-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43107-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43107-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="43107-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43107-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43107-118">См. также</span><span class="sxs-lookup"><span data-stu-id="43107-118">See also</span></span>

- [<span data-ttu-id="43107-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="43107-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
