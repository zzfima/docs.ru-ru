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
ms.openlocfilehash: da1aab48e2eef229bb31e9443a5549c3f9fbc621
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455306"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="2cd36-102">Интерфейс ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="2cd36-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="2cd36-103">[Поддерживается в .NET Framework 4.6 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="2cd36-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="2cd36-104">Подкласс [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) , предоставляющий перечислитель для всех методов, которые определены в указанный модуль NGen и встроенные данный метод.</span><span class="sxs-lookup"><span data-stu-id="2cd36-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2cd36-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2cd36-105">Methods</span></span>  
  
|<span data-ttu-id="2cd36-106">Метод</span><span class="sxs-lookup"><span data-stu-id="2cd36-106">Method</span></span>|<span data-ttu-id="2cd36-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2cd36-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2cd36-108">Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="2cd36-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="2cd36-109">Возвращает перечислитель для всех методов, принадлежащих данного модуля NGen, и, встраиваются в основной части данного метода.</span><span class="sxs-lookup"><span data-stu-id="2cd36-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2cd36-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2cd36-110">Requirements</span></span>  
 <span data-ttu-id="2cd36-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cd36-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cd36-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2cd36-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2cd36-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cd36-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd36-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2cd36-114">See Also</span></span>  
 [<span data-ttu-id="2cd36-115">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="2cd36-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
