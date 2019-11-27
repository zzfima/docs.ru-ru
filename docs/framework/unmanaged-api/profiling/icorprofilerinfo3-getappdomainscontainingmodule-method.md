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
ms.openlocfilehash: 93c042d760eab4bcb1846701ad92ac38cb473c69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449734"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="c55fa-102">Метод ICorProfilerInfo3::GetAppDomainsContainingModule</span><span class="sxs-lookup"><span data-stu-id="c55fa-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>
<span data-ttu-id="c55fa-103">Возвращает идентификаторы доменов приложений, в которые был загружен указанный модуль.</span><span class="sxs-lookup"><span data-stu-id="c55fa-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c55fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c55fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c55fa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c55fa-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="c55fa-106">[in] Идентификатор загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="c55fa-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="c55fa-107">[in] Размер массива `appDomainIds`.</span><span class="sxs-lookup"><span data-stu-id="c55fa-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="c55fa-108">[out] Указатель на общее число возвращенных элементов.</span><span class="sxs-lookup"><span data-stu-id="c55fa-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="c55fa-109">[out] Массив значений идентификаторов доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="c55fa-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c55fa-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="c55fa-110">Remarks</span></span>  
 <span data-ttu-id="c55fa-111">Этот метод использует буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="c55fa-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c55fa-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c55fa-112">Requirements</span></span>  
 <span data-ttu-id="c55fa-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c55fa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c55fa-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c55fa-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c55fa-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c55fa-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c55fa-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c55fa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55fa-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="c55fa-117">See also</span></span>

- [<span data-ttu-id="c55fa-118">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="c55fa-118">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="c55fa-119">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="c55fa-119">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="c55fa-120">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="c55fa-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c55fa-121">Профилирование</span><span class="sxs-lookup"><span data-stu-id="c55fa-121">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
