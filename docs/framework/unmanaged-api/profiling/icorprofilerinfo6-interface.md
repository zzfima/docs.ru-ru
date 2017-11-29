---
title: "Интерфейс ICorProfilerInfo6"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo6
api_location: mscorwks.dll
api_type: COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4ea37d277c3e8176e999de7c5bc527f2677cf25c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="94c94-102">Интерфейс ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="94c94-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="94c94-103">[Поддерживается в .NET Framework 4.6 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="94c94-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="94c94-104">Подкласс [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) , предоставляющий перечислитель для всех методов, которые определены в указанный модуль NGen и встроенные данный метод.</span><span class="sxs-lookup"><span data-stu-id="94c94-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94c94-105">Методы</span><span class="sxs-lookup"><span data-stu-id="94c94-105">Methods</span></span>  
  
|<span data-ttu-id="94c94-106">Метод</span><span class="sxs-lookup"><span data-stu-id="94c94-106">Method</span></span>|<span data-ttu-id="94c94-107">Описание</span><span class="sxs-lookup"><span data-stu-id="94c94-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94c94-108">Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="94c94-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="94c94-109">Возвращает перечислитель для всех методов, принадлежащих данного модуля NGen, и, встраиваются в основной части данного метода.</span><span class="sxs-lookup"><span data-stu-id="94c94-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94c94-110">Требования</span><span class="sxs-lookup"><span data-stu-id="94c94-110">Requirements</span></span>  
 <span data-ttu-id="94c94-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94c94-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94c94-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="94c94-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="94c94-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94c94-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94c94-114">См. также</span><span class="sxs-lookup"><span data-stu-id="94c94-114">See Also</span></span>  
 [<span data-ttu-id="94c94-115">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="94c94-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
