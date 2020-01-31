---
title: Интерфейс ICorProfilerCallback7
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: e61f6a104b8b9613db32ed6912395fd07c18dcff
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864821"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="55074-102">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="55074-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="55074-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="55074-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="55074-104">Подкласс [ICorProfilerCallback6](icorprofilercallback6-interface.md) , который предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика, что обновляется поток символов, связанный с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="55074-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55074-105">Методы</span><span class="sxs-lookup"><span data-stu-id="55074-105">Methods</span></span>  
  
|<span data-ttu-id="55074-106">Метод</span><span class="sxs-lookup"><span data-stu-id="55074-106">Method</span></span>|<span data-ttu-id="55074-107">Описание</span><span class="sxs-lookup"><span data-stu-id="55074-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="55074-108">Метод ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="55074-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="55074-109">Уведомляет профилировщик об обновлении потока символов, связанного с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="55074-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55074-110">Требования</span><span class="sxs-lookup"><span data-stu-id="55074-110">Requirements</span></span>  
 <span data-ttu-id="55074-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55074-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55074-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55074-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55074-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55074-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55074-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="55074-114">See also</span></span>

- [<span data-ttu-id="55074-115">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="55074-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
