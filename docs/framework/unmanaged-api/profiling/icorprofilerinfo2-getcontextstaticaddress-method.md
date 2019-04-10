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
ms.openlocfilehash: 46fd79931e7f2f05b1b17ebca3f8cff28c152ff4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221431"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="0d6fc-102">Метод ICorProfilerInfo2::GetContextStaticAddress</span><span class="sxs-lookup"><span data-stu-id="0d6fc-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="0d6fc-103">Возвращает адрес для указанного поля статического контекста, в рамках заданного контекста.</span><span class="sxs-lookup"><span data-stu-id="0d6fc-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d6fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d6fc-104">Syntax</span></span>  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d6fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d6fc-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="0d6fc-106">[in] Идентификатор класса, содержащего запрошенного контекстно статические поля.</span><span class="sxs-lookup"><span data-stu-id="0d6fc-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="0d6fc-107">[in] Маркер метаданных для запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="0d6fc-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="0d6fc-108">[in] Идентификатор контекста, который является областью для запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="0d6fc-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="0d6fc-109">[out] Указатель на адрес статического поля, в заданном контексте.</span><span class="sxs-lookup"><span data-stu-id="0d6fc-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d6fc-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d6fc-110">Remarks</span></span>  
 <span data-ttu-id="0d6fc-111">`GetContextStaticAddress` Метод может возвращать одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="0d6fc-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="0d6fc-112">HRESULT CORPROF_E_DATAINCOMPLETE, если заданного статические поля не был назначен адрес в заданном контексте.</span><span class="sxs-lookup"><span data-stu-id="0d6fc-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="0d6fc-113">Адреса объектов, которые могут быть в куче сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="0d6fc-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="0d6fc-114">Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора, профилировщики не следует предполагать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="0d6fc-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="0d6fc-115">До завершения конструктора класса `GetContextStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, несмотря на то, что некоторые статические поля уже могут быть инициализированы и болея объекты сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0d6fc-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d6fc-116">Требования</span><span class="sxs-lookup"><span data-stu-id="0d6fc-116">Requirements</span></span>  
 <span data-ttu-id="0d6fc-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d6fc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d6fc-118">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0d6fc-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0d6fc-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d6fc-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0d6fc-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0d6fc-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d6fc-121">См. также</span><span class="sxs-lookup"><span data-stu-id="0d6fc-121">See also</span></span>

- [<span data-ttu-id="0d6fc-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0d6fc-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="0d6fc-123">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="0d6fc-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
