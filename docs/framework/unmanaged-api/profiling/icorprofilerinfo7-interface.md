---
title: Интерфейс ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79a722cd3318def36c20a49c1567c6f0d4989d39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455410"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="d989c-102">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="d989c-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="d989c-103">[Поддерживается в [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="d989c-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="d989c-104">Подкласс [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , предоставляет метод для применения вновь определен метаданных для модуля и, обеспечивающий доступ к поток символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="d989c-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d989c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d989c-105">Methods</span></span>  
  
|<span data-ttu-id="d989c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="d989c-106">Method</span></span>|<span data-ttu-id="d989c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d989c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d989c-108">Метод ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="d989c-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="d989c-109">Применяет метаданные, определяемые вновь `IMetadataEmit::Define*` методы для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="d989c-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="d989c-110">Метод GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="d989c-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="d989c-111">Возвращает длину потока в памяти символа.</span><span class="sxs-lookup"><span data-stu-id="d989c-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="d989c-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="d989c-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="d989c-113">Считывает байт из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="d989c-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d989c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d989c-114">Requirements</span></span>  
 <span data-ttu-id="d989c-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d989c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d989c-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d989c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d989c-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d989c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d989c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d989c-118">See Also</span></span>  
 [<span data-ttu-id="d989c-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="d989c-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
