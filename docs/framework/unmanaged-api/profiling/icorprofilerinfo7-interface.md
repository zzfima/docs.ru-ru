---
title: Интерфейс ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a734bfdef89d4f8f9459f49a3ce2cee83faef9f6
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "66250990"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="aca50-102">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="aca50-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="aca50-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="aca50-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="aca50-104">Подкласс [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , предоставляющий метод для применения вновь определен метаданных для модуля и, обеспечивающий доступ в поток символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="aca50-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aca50-105">Методы</span><span class="sxs-lookup"><span data-stu-id="aca50-105">Methods</span></span>  
  
|<span data-ttu-id="aca50-106">Метод</span><span class="sxs-lookup"><span data-stu-id="aca50-106">Method</span></span>|<span data-ttu-id="aca50-107">Описание</span><span class="sxs-lookup"><span data-stu-id="aca50-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aca50-108">Метод ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="aca50-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="aca50-109">Применяет метаданные, вновь определением `IMetadataEmit::Define*` методов к указанному модулю.</span><span class="sxs-lookup"><span data-stu-id="aca50-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="aca50-110">Метод GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="aca50-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="aca50-111">Возвращает длину потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="aca50-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="aca50-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="aca50-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="aca50-113">Считывает байт из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="aca50-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aca50-114">Требования</span><span class="sxs-lookup"><span data-stu-id="aca50-114">Requirements</span></span>  
 <span data-ttu-id="aca50-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aca50-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aca50-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aca50-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aca50-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aca50-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca50-118">См. также</span><span class="sxs-lookup"><span data-stu-id="aca50-118">See also</span></span>

- [<span data-ttu-id="aca50-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="aca50-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
