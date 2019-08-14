---
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f3c0a3525c87fbf39199c15a6619ff4a0d2acc42
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973854"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="af75f-102">Метод ICorProfilerInfo8:: GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="af75f-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>
  
  <span data-ttu-id="af75f-103">Сопоставляет указатель инструкции управляемого кода с FunctionID.</span><span class="sxs-lookup"><span data-stu-id="af75f-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="af75f-104">Этот метод работает как с динамическими, так и с нединамическими методами.</span><span class="sxs-lookup"><span data-stu-id="af75f-104">This method works for both dynamic and non-dynamic methods.</span></span>    
  
## <a name="syntax"></a><span data-ttu-id="af75f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af75f-105">Syntax</span></span>  
  
```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```  
  
#### <a name="parameters"></a><span data-ttu-id="af75f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="af75f-106">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="af75f-107">окне Указатель инструкции в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="af75f-107">[in] The instruction pointer in managed code.</span></span>  

 `pFunctionId`  
 <span data-ttu-id="af75f-108">заполняет Идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="af75f-108">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="af75f-109">заполняет Удостоверение JIT-повторно скомпилированной версии функции.</span><span class="sxs-lookup"><span data-stu-id="af75f-109">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af75f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="af75f-110">Remarks</span></span>  
 <span data-ttu-id="af75f-111">Этот метод работает как с динамическими, так и с нединамическими методами.</span><span class="sxs-lookup"><span data-stu-id="af75f-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="af75f-112">Это надмножество [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), который работает только для функций с метаданными.</span><span class="sxs-lookup"><span data-stu-id="af75f-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>
  

## <a name="requirements"></a><span data-ttu-id="af75f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="af75f-113">Requirements</span></span>  
 <span data-ttu-id="af75f-114">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af75f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af75f-115">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="af75f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="af75f-116">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="af75f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af75f-117">**.NET Framework версии:** [! ВКЛЮЧИТЬ[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span><span class="sxs-lookup"><span data-stu-id="af75f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af75f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="af75f-118">See also</span></span>
- [<span data-ttu-id="af75f-119">Интерфейс ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="af75f-119">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)

