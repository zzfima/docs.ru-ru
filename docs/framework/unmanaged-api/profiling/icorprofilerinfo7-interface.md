---
title: Интерфейс ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: f80f310c10bae33583cb7cd2048ede4f5efbe14c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861753"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="f1fa5-102">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="f1fa5-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="f1fa5-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="f1fa5-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="f1fa5-104">Подкласс [ICorProfilerInfo6](icorprofilerinfo6-interface.md) , предоставляющий метод для применения вновь заданных метаданных к модулю и предоставляющий доступ к потоку символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="f1fa5-104">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1fa5-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f1fa5-105">Methods</span></span>  
  
|<span data-ttu-id="f1fa5-106">Метод</span><span class="sxs-lookup"><span data-stu-id="f1fa5-106">Method</span></span>|<span data-ttu-id="f1fa5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f1fa5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1fa5-108">Метод ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="f1fa5-108">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="f1fa5-109">Применяет метаданные, которые недавно задаются `IMetadataEmit::Define*` методами, к указанному модулю.</span><span class="sxs-lookup"><span data-stu-id="f1fa5-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="f1fa5-110">Метод GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="f1fa5-110">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="f1fa5-111">Возвращает длину потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="f1fa5-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="f1fa5-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="f1fa5-112">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="f1fa5-113">Считывает байты из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="f1fa5-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1fa5-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f1fa5-114">Requirements</span></span>  
 <span data-ttu-id="f1fa5-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1fa5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1fa5-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1fa5-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1fa5-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1fa5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1fa5-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="f1fa5-118">See also</span></span>

- [<span data-ttu-id="f1fa5-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="f1fa5-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
