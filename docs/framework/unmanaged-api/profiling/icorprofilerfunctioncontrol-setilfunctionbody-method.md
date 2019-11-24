---
title: Метод ICorProfilerFunctionControl::SetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: f6e2cfe47bdd212e39549544b06bf5b11033a956
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429882"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="38c64-102">Метод ICorProfilerFunctionControl::SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="38c64-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="38c64-103">Заменяет тело метода на языке CIL.</span><span class="sxs-lookup"><span data-stu-id="38c64-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38c64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38c64-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38c64-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="38c64-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="38c64-106">[in] Общий размер нового кода CIL, включая заголовок и все структуры после тела.</span><span class="sxs-lookup"><span data-stu-id="38c64-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="38c64-107">[in] Указатель на новый заголовок на языке CIL.</span><span class="sxs-lookup"><span data-stu-id="38c64-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38c64-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="38c64-108">Return Value</span></span>  
 <span data-ttu-id="38c64-109">Этот метод возвращает следующие специфичные результаты HRESULT.</span><span class="sxs-lookup"><span data-stu-id="38c64-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="38c64-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="38c64-110">HRESULT</span></span>|<span data-ttu-id="38c64-111">Описание</span><span class="sxs-lookup"><span data-stu-id="38c64-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="38c64-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="38c64-112">S_OK</span></span>|<span data-ttu-id="38c64-113">Замена выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="38c64-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38c64-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="38c64-114">Remarks</span></span>  
 <span data-ttu-id="38c64-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span><span class="sxs-lookup"><span data-stu-id="38c64-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="38c64-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span><span class="sxs-lookup"><span data-stu-id="38c64-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="38c64-117">Его можно разместить в любой куче.</span><span class="sxs-lookup"><span data-stu-id="38c64-117">It can be allocated on any heap.</span></span> <span data-ttu-id="38c64-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span><span class="sxs-lookup"><span data-stu-id="38c64-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38c64-119">Требования</span><span class="sxs-lookup"><span data-stu-id="38c64-119">Requirements</span></span>  
 <span data-ttu-id="38c64-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38c64-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38c64-121">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38c64-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38c64-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38c64-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38c64-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38c64-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c64-124">См. также</span><span class="sxs-lookup"><span data-stu-id="38c64-124">See also</span></span>

- [<span data-ttu-id="38c64-125">Интерфейс ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="38c64-125">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
