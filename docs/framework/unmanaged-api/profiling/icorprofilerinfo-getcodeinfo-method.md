---
title: Метод ICorProfilerInfo::GetCodeInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCodeInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCodeInfo
helpviewer_keywords:
- GetCodeInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetCodeInfo method [.NET Framework profiling]
ms.assetid: 90140b0f-a926-4a7e-b6fa-23e05f703cce
topic_type:
- apiref
ms.openlocfilehash: 2393468f78312511d11cbe0ab422c26c710e25d8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439238"
---
# <a name="icorprofilerinfogetcodeinfo-method"></a><span data-ttu-id="1603e-102">Метод ICorProfilerInfo::GetCodeInfo</span><span class="sxs-lookup"><span data-stu-id="1603e-102">ICorProfilerInfo::GetCodeInfo Method</span></span>
<span data-ttu-id="1603e-103">Получает экстент машинного кода, связанного с указанным идентификатором функции.</span><span class="sxs-lookup"><span data-stu-id="1603e-103">Gets the extent of native code associated with the specified function ID.</span></span>  
  
 <span data-ttu-id="1603e-104">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="1603e-104">This method is obsolete.</span></span> <span data-ttu-id="1603e-105">Используйте вместо этого метод [ICorProfilerInfo2:: GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1603e-105">Use the [ICorProfilerInfo2::GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1603e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1603e-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1603e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="1603e-107">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="1603e-108">[in] Идентификатор функции, с которым связан машинный код.</span><span class="sxs-lookup"><span data-stu-id="1603e-108">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `pStart`  
 <span data-ttu-id="1603e-109">[out] Указатель на массив байтов, составляющих машинный код функции.</span><span class="sxs-lookup"><span data-stu-id="1603e-109">[out] A pointer to an array of bytes that compose the native code of the function.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="1603e-110">[out] Указатель на целое число, задающее размер машинного кода в байтах.</span><span class="sxs-lookup"><span data-stu-id="1603e-110">[out] A pointer to an integer that specifies the size, in bytes, of the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1603e-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="1603e-111">Remarks</span></span>  
 <span data-ttu-id="1603e-112">Для оптимизации производительности среда выполнения в .NET Framework версии 2.0 разделяет предварительно скомпилированный машинный код функции на несколько областей.</span><span class="sxs-lookup"><span data-stu-id="1603e-112">To optimize performance, the runtime in the .NET Framework version 2.0 splits the precompiled, native code of a function into multiple regions.</span></span> <span data-ttu-id="1603e-113">Следовательно, метод `GetCodeInfo` является устаревшим в .NET Framework 2.0, так как он не может обработать экстент машинного кода функции.</span><span class="sxs-lookup"><span data-stu-id="1603e-113">Consequently, the `GetCodeInfo` method is obsolete in the .NET Framework 2.0 because it is unable to handle the extent of a function's native code.</span></span> <span data-ttu-id="1603e-114">Профилировщики следует переключить на использование более универсального метода `ICorProfilerInfo2::GetCodeInfo2`.</span><span class="sxs-lookup"><span data-stu-id="1603e-114">Profilers should switch to using the more general `ICorProfilerInfo2::GetCodeInfo2` method instead.</span></span>  
  
 <span data-ttu-id="1603e-115">Эта функция использует буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="1603e-115">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1603e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="1603e-116">Requirements</span></span>  
 <span data-ttu-id="1603e-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1603e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1603e-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1603e-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1603e-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1603e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1603e-120">**.NET Framework версии:** 1,0</span><span class="sxs-lookup"><span data-stu-id="1603e-120">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1603e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="1603e-121">See also</span></span>

- [<span data-ttu-id="1603e-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1603e-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="1603e-123">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="1603e-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="1603e-124">Профилирование</span><span class="sxs-lookup"><span data-stu-id="1603e-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
