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
ms.openlocfilehash: 80ac17a96e5c1c8c32cfc336da6c2be30eaf80fd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868373"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="cf96b-102">Интерфейс ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="cf96b-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="cf96b-103">[Поддерживается в .NET Framework 4,6 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="cf96b-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="cf96b-104">Подкласс [ICorProfilerInfo5](icorprofilerinfo5-interface.md) , предоставляющий перечислитель для всех методов, определенных в заданном модуле NGen, и встроенный метод.</span><span class="sxs-lookup"><span data-stu-id="cf96b-104">A subclass of [ICorProfilerInfo5](icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cf96b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="cf96b-105">Methods</span></span>  
  
|<span data-ttu-id="cf96b-106">Метод</span><span class="sxs-lookup"><span data-stu-id="cf96b-106">Method</span></span>|<span data-ttu-id="cf96b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cf96b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cf96b-108">Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="cf96b-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="cf96b-109">Возвращает перечислитель для всех методов, принадлежащих заданному модулю NGen и встроенных в тело данного метода.</span><span class="sxs-lookup"><span data-stu-id="cf96b-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf96b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="cf96b-110">Requirements</span></span>  
 <span data-ttu-id="cf96b-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf96b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf96b-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf96b-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf96b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf96b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf96b-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf96b-114">See also</span></span>

- [<span data-ttu-id="cf96b-115">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="cf96b-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
