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
ms.openlocfilehash: 9c971df072cc7c6546e5c17278c78c7e9668ab63
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780636"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="a19dd-102">Метод ICorProfilerInfo::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="a19dd-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="a19dd-103">Получает идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="a19dd-103">Gets the ID of a function.</span></span> <span data-ttu-id="a19dd-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="a19dd-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a19dd-105">Используйте [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="a19dd-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a19dd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a19dd-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a19dd-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a19dd-107">Remarks</span></span>  
 <span data-ttu-id="a19dd-108">`GetFunctionFromToken` Метод не будет работать для универсальных функций или функций в универсальных типах; теперь является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="a19dd-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="a19dd-109">Используйте `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` для всех функций.</span><span class="sxs-lookup"><span data-stu-id="a19dd-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a19dd-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a19dd-110">Requirements</span></span>  
 <span data-ttu-id="a19dd-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a19dd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a19dd-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a19dd-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a19dd-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a19dd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a19dd-114">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="a19dd-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a19dd-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a19dd-115">See also</span></span>

- [<span data-ttu-id="a19dd-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="a19dd-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
