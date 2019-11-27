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
ms.openlocfilehash: 0a3ec1a317fbeba2bf792378663e2fe940a8ec10
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439116"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="db6be-102">Метод ICorProfilerInfo::GetFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="db6be-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="db6be-103">Возвращает родительский класс и токен метаданных для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="db6be-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db6be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db6be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db6be-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="db6be-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="db6be-106">окне Идентификатор функции, для которой необходимо получить родительский класс и маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="db6be-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="db6be-107">[выходной] Указатель на родительский класс функции.</span><span class="sxs-lookup"><span data-stu-id="db6be-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="db6be-108">[выходной] Указатель на модуль, в котором определен родительский класс функции.</span><span class="sxs-lookup"><span data-stu-id="db6be-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="db6be-109">[выходной] Указатель на токен метаданных функции.</span><span class="sxs-lookup"><span data-stu-id="db6be-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db6be-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="db6be-110">Remarks</span></span>  
 <span data-ttu-id="db6be-111">Чтобы получить интерфейс метаданных для заданного модуля, код профилировщика может вызвать метод [ICorProfilerInfo:: жетмодулеметадата](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) .</span><span class="sxs-lookup"><span data-stu-id="db6be-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="db6be-112">Токен метаданных, возвращенный в расположение, на которое ссылается `pToken`, можно впоследствии использовать для доступа к метаданным функции.</span><span class="sxs-lookup"><span data-stu-id="db6be-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="db6be-113">`ClassID` функции в универсальном классе может быть невозможно получить без более контекстной информации об использовании функции.</span><span class="sxs-lookup"><span data-stu-id="db6be-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="db6be-114">В этом случае `pClassId` будет иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="db6be-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="db6be-115">Для предоставления большего контекста в коде профилировщика следует использовать [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) со значением COR_PRF_FRAME_INFO.</span><span class="sxs-lookup"><span data-stu-id="db6be-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db6be-116">Требования</span><span class="sxs-lookup"><span data-stu-id="db6be-116">Requirements</span></span>  
 <span data-ttu-id="db6be-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db6be-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db6be-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db6be-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db6be-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db6be-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db6be-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db6be-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db6be-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="db6be-121">See also</span></span>

- [<span data-ttu-id="db6be-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="db6be-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
