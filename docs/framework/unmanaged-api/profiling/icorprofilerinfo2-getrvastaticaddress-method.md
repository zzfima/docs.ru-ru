---
title: Метод ICorProfilerInfo2::GetRVAStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9390fd62e001b02b6b6d758bb65a45ab847e89c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564098"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="c3990-102">Метод ICorProfilerInfo2::GetRVAStaticAddress</span><span class="sxs-lookup"><span data-stu-id="c3990-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="c3990-103">Возвращает адрес указанного относительного виртуального адреса (RVA) статического поля.</span><span class="sxs-lookup"><span data-stu-id="c3990-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3990-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3990-104">Syntax</span></span>  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3990-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3990-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="c3990-106">[in] Идентификатор класса, содержащего запрошенный RVA-статического поля.</span><span class="sxs-lookup"><span data-stu-id="c3990-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="c3990-107">[in] Токен метаданных для запрошенного RVA статического поля.</span><span class="sxs-lookup"><span data-stu-id="c3990-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="c3990-108">[out] Указатель на адрес RVA статического поля.</span><span class="sxs-lookup"><span data-stu-id="c3990-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3990-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3990-109">Remarks</span></span>  
 <span data-ttu-id="c3990-110">`GetRVAStaticAddress` Метод может возвращать одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="c3990-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="c3990-111">HRESULT CORPROF_E_DATAINCOMPLETE, если заданного статические поля не был назначен адрес в заданном контексте.</span><span class="sxs-lookup"><span data-stu-id="c3990-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="c3990-112">Адреса объектов, которые могут быть в куче сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="c3990-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="c3990-113">Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора, профилировщики не следует предполагать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="c3990-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="c3990-114">До завершения конструктора класса `GetRVAStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, несмотря на то, что некоторые статические поля уже могут быть инициализированы и могут маршрутизировать объекты сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c3990-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3990-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c3990-115">Requirements</span></span>  
 <span data-ttu-id="c3990-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3990-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3990-117">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3990-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c3990-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3990-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3990-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3990-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3990-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c3990-120">See also</span></span>
- [<span data-ttu-id="c3990-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="c3990-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="c3990-122">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="c3990-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
