---
title: Метод ICorProfilerInfo2::GetContextStaticAddress
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d787e3eae59218c46a95c327a0f93502c3833d9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="b58be-102">Метод ICorProfilerInfo2::GetContextStaticAddress</span><span class="sxs-lookup"><span data-stu-id="b58be-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="b58be-103">Возвращает адрес для указанного поля статического контекста, который находится в области заданного контекста.</span><span class="sxs-lookup"><span data-stu-id="b58be-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b58be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b58be-104">Syntax</span></span>  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b58be-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b58be-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="b58be-106">[in] Идентификатор класса, содержащего запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="b58be-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="b58be-107">[in] Токен метаданных для запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="b58be-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="b58be-108">[in] Идентификатор контекста, область для запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="b58be-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="b58be-109">[out] Указатель на адрес статического поля, которое находится в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="b58be-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b58be-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="b58be-110">Remarks</span></span>  
 <span data-ttu-id="b58be-111">`GetContextStaticAddress` Метод может возвращать одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="b58be-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="b58be-112">CORPROF_E_DATAINCOMPLETE HRESULT, если заданного статического поля не был назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="b58be-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="b58be-113">Адреса объектов, которые могут находиться в куче сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="b58be-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="b58be-114">Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора профилировщики не следует предполагать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="b58be-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="b58be-115">До завершения конструктора класса `GetContextStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, хотя некоторые статические поля уже могут быть инициализированы и болея объекты сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b58be-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b58be-116">Требования</span><span class="sxs-lookup"><span data-stu-id="b58be-116">Requirements</span></span>  
 <span data-ttu-id="b58be-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b58be-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b58be-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b58be-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b58be-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b58be-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b58be-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b58be-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b58be-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b58be-121">See Also</span></span>  
 [<span data-ttu-id="b58be-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b58be-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="b58be-123">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="b58be-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
