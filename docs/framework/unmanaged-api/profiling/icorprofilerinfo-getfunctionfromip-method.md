---
title: Метод ICorProfilerInfo::GetFunctionFromIP
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
ms.openlocfilehash: cd1f3982fe1439135bf96579370a5a798c61dd2e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863807"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="e6c88-102">Метод ICorProfilerInfo::GetFunctionFromIP</span><span class="sxs-lookup"><span data-stu-id="e6c88-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="e6c88-103">Сопоставляет указатель инструкции управляемого кода с `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="e6c88-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6c88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6c88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6c88-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6c88-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="e6c88-106">\[in] указатель инструкций в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="e6c88-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="e6c88-107">\[out] возвращаемый идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="e6c88-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6c88-108">Требования</span><span class="sxs-lookup"><span data-stu-id="e6c88-108">Requirements</span></span>  
 <span data-ttu-id="e6c88-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6c88-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6c88-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6c88-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6c88-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6c88-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6c88-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6c88-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6c88-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6c88-113">See also</span></span>

- [<span data-ttu-id="e6c88-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e6c88-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
