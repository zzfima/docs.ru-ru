---
title: Интерфейс ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 4c7e94ffa60bcfaead009e1a8baa9b54b2e8ab7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125056"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="ab9a4-102">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="ab9a4-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="ab9a4-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="ab9a4-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="ab9a4-104">Подкласс [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) , предоставляющий метод для применения вновь заданных метаданных к модулю и предоставляющий доступ к потоку символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="ab9a4-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab9a4-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ab9a4-105">Methods</span></span>  
  
|<span data-ttu-id="ab9a4-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ab9a4-106">Method</span></span>|<span data-ttu-id="ab9a4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ab9a4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ab9a4-108">Метод ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="ab9a4-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="ab9a4-109">Применяет метаданные, которые недавно задаются `IMetadataEmit::Define*` методами, к указанному модулю.</span><span class="sxs-lookup"><span data-stu-id="ab9a4-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="ab9a4-110">Метод GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="ab9a4-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="ab9a4-111">Возвращает длину потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="ab9a4-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="ab9a4-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="ab9a4-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="ab9a4-113">Считывает байты из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="ab9a4-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab9a4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ab9a4-114">Requirements</span></span>  
 <span data-ttu-id="ab9a4-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab9a4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab9a4-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ab9a4-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ab9a4-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab9a4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab9a4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ab9a4-118">See also</span></span>

- [<span data-ttu-id="ab9a4-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="ab9a4-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
