---
title: Метод ICorProfilerInfo3::GetAppDomainsContainingModule
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5658ac87c7a938381639442216df03853f02998
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195791"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="ebccc-102">Метод ICorProfilerInfo3::GetAppDomainsContainingModule</span><span class="sxs-lookup"><span data-stu-id="ebccc-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>
<span data-ttu-id="ebccc-103">Возвращает идентификаторы доменов приложений, в которые был загружен указанный модуль.</span><span class="sxs-lookup"><span data-stu-id="ebccc-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebccc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebccc-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebccc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebccc-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ebccc-106">[in] Идентификатор загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="ebccc-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="ebccc-107">[in] Размер массива `appDomainIds`.</span><span class="sxs-lookup"><span data-stu-id="ebccc-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="ebccc-108">[out] Указатель на общее число возвращенных элементов.</span><span class="sxs-lookup"><span data-stu-id="ebccc-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="ebccc-109">[out] Массив значений идентификаторов доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="ebccc-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebccc-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ebccc-110">Remarks</span></span>  
 <span data-ttu-id="ebccc-111">Этот метод использует буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="ebccc-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebccc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ebccc-112">Requirements</span></span>  
 <span data-ttu-id="ebccc-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebccc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebccc-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ebccc-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ebccc-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebccc-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ebccc-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ebccc-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ebccc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ebccc-117">See also</span></span>

- [<span data-ttu-id="ebccc-118">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="ebccc-118">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="ebccc-119">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="ebccc-119">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="ebccc-120">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="ebccc-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ebccc-121">Профилирование</span><span class="sxs-lookup"><span data-stu-id="ebccc-121">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
