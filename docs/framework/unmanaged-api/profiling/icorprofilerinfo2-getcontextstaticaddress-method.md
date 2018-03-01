---
title: "Метод ICorProfilerInfo2::GetContextStaticAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e92435927203bb2a75ff92d883470832126da080
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="fa81d-102">Метод ICorProfilerInfo2::GetContextStaticAddress</span><span class="sxs-lookup"><span data-stu-id="fa81d-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="fa81d-103">Возвращает адрес для указанного поля статического контекста, который находится в области заданного контекста.</span><span class="sxs-lookup"><span data-stu-id="fa81d-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa81d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa81d-104">Syntax</span></span>  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa81d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa81d-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="fa81d-106">[in] Идентификатор класса, содержащего запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="fa81d-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="fa81d-107">[in] Токен метаданных для запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="fa81d-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="fa81d-108">[in] Идентификатор контекста, область для запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="fa81d-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="fa81d-109">[out] Указатель на адрес статического поля, которое находится в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="fa81d-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa81d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa81d-110">Remarks</span></span>  
 <span data-ttu-id="fa81d-111">`GetContextStaticAddress` Метод может возвращать одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="fa81d-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="fa81d-112">CORPROF_E_DATAINCOMPLETE HRESULT, если заданного статического поля не был назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="fa81d-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="fa81d-113">Адреса объектов, которые могут находиться в куче сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="fa81d-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="fa81d-114">Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора профилировщики не следует предполагать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="fa81d-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="fa81d-115">До завершения конструктора класса `GetContextStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, хотя некоторые статические поля уже могут быть инициализированы и болея объекты сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="fa81d-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa81d-116">Требования</span><span class="sxs-lookup"><span data-stu-id="fa81d-116">Requirements</span></span>  
 <span data-ttu-id="fa81d-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa81d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa81d-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa81d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa81d-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa81d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa81d-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa81d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa81d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="fa81d-121">See Also</span></span>  
 [<span data-ttu-id="fa81d-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="fa81d-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="fa81d-123">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="fa81d-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
