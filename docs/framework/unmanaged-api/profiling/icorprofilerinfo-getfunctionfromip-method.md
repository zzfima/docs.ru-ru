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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fba01c1dfdea83b2580f45b7dbcef91fb7b73fb2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="9272b-102">Метод ICorProfilerInfo::GetFunctionFromIP</span><span class="sxs-lookup"><span data-stu-id="9272b-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="9272b-103">Сопоставляет указатель инструкции управляемого кода `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="9272b-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9272b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9272b-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9272b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9272b-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="9272b-106">[in] Указатель инструкций в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="9272b-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="9272b-107">[out] Идентификатор возвращаемой функции.</span><span class="sxs-lookup"><span data-stu-id="9272b-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9272b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9272b-108">Requirements</span></span>  
 <span data-ttu-id="9272b-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9272b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9272b-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9272b-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9272b-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9272b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9272b-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9272b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9272b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9272b-113">See Also</span></span>  
 [<span data-ttu-id="9272b-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="9272b-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
