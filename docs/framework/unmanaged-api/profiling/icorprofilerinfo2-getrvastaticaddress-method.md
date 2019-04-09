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
ms.openlocfilehash: d3749c600d54671071efbec8322e050cde446c27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158617"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="33ced-102">Метод ICorProfilerInfo2::GetRVAStaticAddress</span><span class="sxs-lookup"><span data-stu-id="33ced-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="33ced-103">Возвращает адрес указанного относительного виртуального адреса (RVA) статического поля.</span><span class="sxs-lookup"><span data-stu-id="33ced-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33ced-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33ced-104">Syntax</span></span>  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33ced-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="33ced-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="33ced-106">[in] Идентификатор класса, содержащего запрошенный RVA-статического поля.</span><span class="sxs-lookup"><span data-stu-id="33ced-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="33ced-107">[in] Токен метаданных для запрошенного RVA статического поля.</span><span class="sxs-lookup"><span data-stu-id="33ced-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="33ced-108">[out] Указатель на адрес RVA статического поля.</span><span class="sxs-lookup"><span data-stu-id="33ced-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33ced-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="33ced-109">Remarks</span></span>  
 <span data-ttu-id="33ced-110">`GetRVAStaticAddress` Метод может возвращать одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="33ced-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="33ced-111">HRESULT CORPROF_E_DATAINCOMPLETE, если заданного статические поля не был назначен адрес в заданном контексте.</span><span class="sxs-lookup"><span data-stu-id="33ced-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="33ced-112">Адреса объектов, которые могут быть в куче сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="33ced-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="33ced-113">Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора, профилировщики не следует предполагать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="33ced-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="33ced-114">До завершения конструктора класса `GetRVAStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, несмотря на то, что некоторые статические поля уже могут быть инициализированы и могут маршрутизировать объекты сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="33ced-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33ced-115">Требования</span><span class="sxs-lookup"><span data-stu-id="33ced-115">Requirements</span></span>  
 <span data-ttu-id="33ced-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33ced-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33ced-117">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33ced-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33ced-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33ced-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="33ced-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="33ced-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33ced-120">См. также</span><span class="sxs-lookup"><span data-stu-id="33ced-120">See also</span></span>

- [<span data-ttu-id="33ced-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="33ced-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="33ced-122">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="33ced-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
