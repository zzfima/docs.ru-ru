---
title: "Метод ICorProfilerInfo::GetFunctionFromToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetFunctionFromToken
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c7366df7d2213740f640590364b1cb4d28876115
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="195b7-102">Метод ICorProfilerInfo::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="195b7-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="195b7-103">Получает идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="195b7-103">Gets the ID of a function.</span></span> <span data-ttu-id="195b7-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="195b7-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="195b7-105">Используйте [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="195b7-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="195b7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="195b7-106">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="195b7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="195b7-107">Remarks</span></span>  
 <span data-ttu-id="195b7-108">`GetFunctionFromToken` Метод не будет работать для универсальных функций или функций в универсальных типах; больше не используется.</span><span class="sxs-lookup"><span data-stu-id="195b7-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="195b7-109">Используйте `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` для всех функций.</span><span class="sxs-lookup"><span data-stu-id="195b7-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="195b7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="195b7-110">Requirements</span></span>  
 <span data-ttu-id="195b7-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="195b7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="195b7-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="195b7-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="195b7-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="195b7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="195b7-114">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="195b7-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195b7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="195b7-115">See Also</span></span>  
 [<span data-ttu-id="195b7-116">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="195b7-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
