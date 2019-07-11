---
title: Метод ICorProfilerInfo::GetFunctionInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b4b39e53af7abaf25cc4a563bfbec8450b1e57d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780656"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="cf1ec-102">Метод ICorProfilerInfo::GetFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="cf1ec-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="cf1ec-103">Получает маркер родительского класса и метаданные для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf1ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf1ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf1ec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf1ec-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="cf1ec-106">[in] Идентификатор функции, для которого нужно получить родительский класс и метаданных маркера.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="cf1ec-107">[выходной] Указатель на родительский класс функции.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="cf1ec-108">[выходной] Указатель на модуль, в котором определен родительский класс функции.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="cf1ec-109">[выходной] Указатель на токен метаданных функции.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf1ec-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="cf1ec-110">Remarks</span></span>  
 <span data-ttu-id="cf1ec-111">Профилировщик кода может вызвать [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) получить интерфейс метаданных для данного модуля.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="cf1ec-112">Токен метаданных, возвращенный в расположение, на которое ссылается `pToken`, можно впоследствии использовать для доступа к метаданным функции.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="cf1ec-113">`ClassID` Функции к универсальному классу может быть доступная без дополнительные контекстные сведения об использовании функции.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="cf1ec-114">В этом случае `pClassId` будет иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="cf1ec-115">Следует использовать код Profiler [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) со значением COR_PRF_FRAME_INFO для предоставления дополнительного контекста.</span><span class="sxs-lookup"><span data-stu-id="cf1ec-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf1ec-116">Требования</span><span class="sxs-lookup"><span data-stu-id="cf1ec-116">Requirements</span></span>  
 <span data-ttu-id="cf1ec-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf1ec-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf1ec-118">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf1ec-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf1ec-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf1ec-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf1ec-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf1ec-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf1ec-121">См. также</span><span class="sxs-lookup"><span data-stu-id="cf1ec-121">See also</span></span>

- [<span data-ttu-id="cf1ec-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="cf1ec-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
