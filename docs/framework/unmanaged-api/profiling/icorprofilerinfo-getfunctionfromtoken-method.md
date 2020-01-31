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
ms.openlocfilehash: 2b2d619c5940376806e9873a528b4f08886593e9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863560"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="16d3e-102">Метод ICorProfilerInfo::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="16d3e-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="16d3e-103">Возвращает идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="16d3e-103">Gets the ID of a function.</span></span> <span data-ttu-id="16d3e-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="16d3e-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="16d3e-105">Используйте вместо этого метод [ICorProfilerInfo2:: жетфунктионфромтокенандтипеаргс](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="16d3e-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d3e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16d3e-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="16d3e-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="16d3e-107">Remarks</span></span>  
 <span data-ttu-id="16d3e-108">Метод `GetFunctionFromToken` не будет работать для универсальных функций или функций в универсальных типах. Теперь она устарела.</span><span class="sxs-lookup"><span data-stu-id="16d3e-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="16d3e-109">Используйте `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` для всех функций.</span><span class="sxs-lookup"><span data-stu-id="16d3e-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16d3e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="16d3e-110">Requirements</span></span>  
 <span data-ttu-id="16d3e-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16d3e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16d3e-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="16d3e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="16d3e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16d3e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16d3e-114">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="16d3e-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16d3e-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="16d3e-115">See also</span></span>

- [<span data-ttu-id="16d3e-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="16d3e-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
