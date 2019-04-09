---
title: Интерфейс ICorProfilerInfo6
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: febe130b4d61b6179aeab3bfcd63891c38b13fbe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128938"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="f1e46-102">Интерфейс ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="f1e46-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="f1e46-103">[Поддерживается в .NET Framework 4.6 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="f1e46-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="f1e46-104">Подкласс [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) , предоставляющий перечислитель для всех методов, которые определены в указанный модуль NGen и в строке данного метода.</span><span class="sxs-lookup"><span data-stu-id="f1e46-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1e46-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f1e46-105">Methods</span></span>  
  
|<span data-ttu-id="f1e46-106">Метод</span><span class="sxs-lookup"><span data-stu-id="f1e46-106">Method</span></span>|<span data-ttu-id="f1e46-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f1e46-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1e46-108">Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="f1e46-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="f1e46-109">Возвращает перечислитель для всех методов, которые принадлежат данного модуля NGen и, встраиваются в тексте данного метода.</span><span class="sxs-lookup"><span data-stu-id="f1e46-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1e46-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f1e46-110">Requirements</span></span>  
 <span data-ttu-id="f1e46-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1e46-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1e46-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1e46-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="f1e46-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f1e46-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f1e46-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f1e46-114">See also</span></span>

- [<span data-ttu-id="f1e46-115">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f1e46-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
