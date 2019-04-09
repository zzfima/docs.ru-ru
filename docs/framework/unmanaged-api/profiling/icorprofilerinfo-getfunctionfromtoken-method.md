---
title: Метод ICorProfilerInfo::GetFunctionFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f4fb2292154a2660a2db3f0b3962fcf2114e385
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099980"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="16b9f-102">Метод ICorProfilerInfo::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="16b9f-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="16b9f-103">Получает идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="16b9f-103">Gets the ID of a function.</span></span> <span data-ttu-id="16b9f-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="16b9f-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="16b9f-105">Используйте [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="16b9f-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16b9f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16b9f-106">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="16b9f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="16b9f-107">Remarks</span></span>  
 <span data-ttu-id="16b9f-108">`GetFunctionFromToken` Метод не будет работать для универсальных функций или функций в универсальных типах; теперь является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="16b9f-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="16b9f-109">Используйте `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` для всех функций.</span><span class="sxs-lookup"><span data-stu-id="16b9f-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16b9f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="16b9f-110">Requirements</span></span>  
 <span data-ttu-id="16b9f-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16b9f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16b9f-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="16b9f-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="16b9f-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16b9f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16b9f-114">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="16b9f-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b9f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="16b9f-115">See also</span></span>

- [<span data-ttu-id="16b9f-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="16b9f-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
