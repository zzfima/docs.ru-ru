---
title: "Метод ICorProfilerInfo2::GetCodeInfo2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetCodeInfo2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetCodeInfo2
helpviewer_keywords:
- ICorProfilerInfo2::GetCodeInfo2 method [.NET Framework profiling]
- GetCodeInfo2 method [.NET Framework profiling]
ms.assetid: 532da6ee-7f0a-401b-a61e-fc47ec235d2e
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b211ba79de7454361b44c6e9852ad6698c2e71c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a><span data-ttu-id="c12f7-102">Метод ICorProfilerInfo2::GetCodeInfo2</span><span class="sxs-lookup"><span data-stu-id="c12f7-102">ICorProfilerInfo2::GetCodeInfo2 Method</span></span>
<span data-ttu-id="c12f7-103">Получает экстенты машинного кода, связанного с указанным `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="c12f7-103">Gets the extents of native code associated with the specified `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c12f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c12f7-104">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c12f7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c12f7-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="c12f7-106">[in] Идентификатор функции, с которым связан машинный код.</span><span class="sxs-lookup"><span data-stu-id="c12f7-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="c12f7-107">[in] Размер массива `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="c12f7-107">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="c12f7-108">[out] Указатель на общее число [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) доступных структур.</span><span class="sxs-lookup"><span data-stu-id="c12f7-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="c12f7-109">[out] Буфер, предоставляемый вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="c12f7-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="c12f7-110">После возврата метода он содержит массив структур `COR_PRF_CODE_INFO`, каждая из которых описывает блок машинного кода.</span><span class="sxs-lookup"><span data-stu-id="c12f7-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c12f7-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c12f7-111">Remarks</span></span>  
 <span data-ttu-id="c12f7-112">Экстенты сортируются в порядке возрастания смещения MCIL.</span><span class="sxs-lookup"><span data-stu-id="c12f7-112">The extents are sorted in order of increasing Microsoft intermediate language (MSIL) offset.</span></span>  
  
 <span data-ttu-id="c12f7-113">После возврата метода `GetCodeInfo2` необходимо убедиться, что буфер `codeInfos` был достаточно велик, чтобы вместить в себя все структуры `COR_PRF_CODE_INFO`.</span><span class="sxs-lookup"><span data-stu-id="c12f7-113">After `GetCodeInfo2` returns, you must verify that the `codeInfos` buffer was large enough to contain all the `COR_PRF_CODE_INFO` structures.</span></span> <span data-ttu-id="c12f7-114">Для этого сравните значение параметра `cCodeInfos` со значением параметра `cchName`.</span><span class="sxs-lookup"><span data-stu-id="c12f7-114">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="c12f7-115">Если значение `cCodeInfos`, деленное на размер структуры `COR_PRF_CODE_INFO`, меньше значения `pcCodeInfos`, выделите буфер `codeInfos` большего размера, обновите параметр `cCodeInfos`, задав новый, больший размер, и вызовите метод `GetCodeInfo2` снова.</span><span class="sxs-lookup"><span data-stu-id="c12f7-115">If `cCodeInfos` divided by the size of a `COR_PRF_CODE_INFO` structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo2` again.</span></span>  
  
 <span data-ttu-id="c12f7-116">Кроме того, сначала можно вызвать метод `GetCodeInfo2` с буфером `codeInfos` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="c12f7-116">Alternatively, you can first call `GetCodeInfo2` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="c12f7-117">Затем можно задать размер буфера `codeInfos` равным значению, возвращенному в параметре `pcCodeInfos` и умноженному на размер структуры `COR_PRF_CODE_INFO`, и вызвать метод `GetCodeInfo2` снова.</span><span class="sxs-lookup"><span data-stu-id="c12f7-117">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a `COR_PRF_CODE_INFO` structure, and call `GetCodeInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c12f7-118">Требования</span><span class="sxs-lookup"><span data-stu-id="c12f7-118">Requirements</span></span>  
 <span data-ttu-id="c12f7-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c12f7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c12f7-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c12f7-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c12f7-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c12f7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c12f7-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c12f7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c12f7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c12f7-123">See Also</span></span>  
 [<span data-ttu-id="c12f7-124">Метод GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="c12f7-124">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)  
 [<span data-ttu-id="c12f7-125">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="c12f7-125">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="c12f7-126">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="c12f7-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="c12f7-127">Профилирование</span><span class="sxs-lookup"><span data-stu-id="c12f7-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
