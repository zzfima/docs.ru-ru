---
title: Интерфейс ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c33e620b861f1065f95ba9f1f732911723c16f88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526279"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="309ee-102">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="309ee-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="309ee-103">[Поддерживается в [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="309ee-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="309ee-104">Подкласс [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , предоставляющий метод для применения вновь определен метаданных для модуля и, обеспечивающий доступ в поток символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="309ee-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="309ee-105">Методы</span><span class="sxs-lookup"><span data-stu-id="309ee-105">Methods</span></span>  
  
|<span data-ttu-id="309ee-106">Метод</span><span class="sxs-lookup"><span data-stu-id="309ee-106">Method</span></span>|<span data-ttu-id="309ee-107">Описание</span><span class="sxs-lookup"><span data-stu-id="309ee-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="309ee-108">Метод ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="309ee-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="309ee-109">Применяет метаданные, вновь определением `IMetadataEmit::Define*` методов к указанному модулю.</span><span class="sxs-lookup"><span data-stu-id="309ee-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="309ee-110">Метод GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="309ee-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="309ee-111">Возвращает длину потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="309ee-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="309ee-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="309ee-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="309ee-113">Считывает байт из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="309ee-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="309ee-114">Требования</span><span class="sxs-lookup"><span data-stu-id="309ee-114">Requirements</span></span>  
 <span data-ttu-id="309ee-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="309ee-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="309ee-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="309ee-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="309ee-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="309ee-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="309ee-118">См. также</span><span class="sxs-lookup"><span data-stu-id="309ee-118">See also</span></span>
- [<span data-ttu-id="309ee-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="309ee-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
