---
title: Метод ICorProfilerInfo::GetModuleInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleInfo
helpviewer_keywords:
- GetModuleInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleInfo method [.NET Framework profiling]
ms.assetid: 5a90d16f-7929-4987-8f83-a631becf564d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69db53c03d68e30507ff3ab2b11b663970d59af0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090814"
---
# <a name="icorprofilerinfogetmoduleinfo-method"></a><span data-ttu-id="fb277-102">Метод ICorProfilerInfo::GetModuleInfo</span><span class="sxs-lookup"><span data-stu-id="fb277-102">ICorProfilerInfo::GetModuleInfo Method</span></span>
<span data-ttu-id="fb277-103">Возвращает имя файла модуля и идентификатор его родительской сборки для указанного идентификатора модуля.</span><span class="sxs-lookup"><span data-stu-id="fb277-103">Given a module ID, returns the file name of the module and the ID of the module's parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb277-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb277-104">Syntax</span></span>  
  
```  
HRESULT GetModuleInfo(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb277-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb277-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="fb277-106">[in] Идентификатор модуля, для которого будут извлекаться сведения.</span><span class="sxs-lookup"><span data-stu-id="fb277-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="fb277-107">[out] Базовый адрес, по которому модуль был загружен.</span><span class="sxs-lookup"><span data-stu-id="fb277-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="fb277-108">[in] Длина буфера возврата `szName` в символах.</span><span class="sxs-lookup"><span data-stu-id="fb277-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="fb277-109">[out] Указатель на общую длину возвращаемого имени файла модуля в символах.</span><span class="sxs-lookup"><span data-stu-id="fb277-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="fb277-110">[out] Буфер расширенных символов, предоставленный вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="fb277-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="fb277-111">При возврате метода этот буфер содержит имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="fb277-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="fb277-112">[out] Указатель на идентификатор родительской сборки модуля.</span><span class="sxs-lookup"><span data-stu-id="fb277-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb277-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb277-113">Remarks</span></span>  
 <span data-ttu-id="fb277-114">Для динамических модулей параметр `szName` является пустой строкой, а базовый адрес равен 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="fb277-114">For dynamic modules, the `szName` parameter is an empty string, and the base address is 0 (zero).</span></span>  
  
 <span data-ttu-id="fb277-115">Несмотря на то что `GetModuleInfo` метод может вызываться сразу же существует идентификатор модуля, идентификатор родительской сборки будет недоступен до получения профилировщиком [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="fb277-115">Although the `GetModuleInfo` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="fb277-116">После возврата метода `GetModuleInfo` необходимо убедиться, что буфер `szName` был достаточно велик, чтобы вместить в себя полное имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="fb277-116">When `GetModuleInfo` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="fb277-117">Для этого сравните значение, на которое указывает параметр `pcchName`, со значением параметра `cchName`.</span><span class="sxs-lookup"><span data-stu-id="fb277-117">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="fb277-118">Если параметр `pcchName` указывает на значение, превышающее значение `cchName`, выделите буфер `szName` большего размера, обновите параметр `cchName`, задав новый, больший размер, и вызовите метод `GetModuleInfo` снова.</span><span class="sxs-lookup"><span data-stu-id="fb277-118">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo` again.</span></span>  
  
 <span data-ttu-id="fb277-119">Кроме того, сначала можно вызвать метод `GetModuleInfo` с буфером `szName` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="fb277-119">Alternatively, you can first call `GetModuleInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="fb277-120">Затем можно задать размер буфера равным значению, возвращенному в параметре `pcchName`, и вызвать метод `GetModuleInfo` снова.</span><span class="sxs-lookup"><span data-stu-id="fb277-120">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb277-121">Требования</span><span class="sxs-lookup"><span data-stu-id="fb277-121">Requirements</span></span>  
 <span data-ttu-id="fb277-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb277-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb277-123">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb277-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb277-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb277-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fb277-125">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fb277-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb277-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fb277-126">See also</span></span>

- [<span data-ttu-id="fb277-127">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="fb277-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="fb277-128">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="fb277-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="fb277-129">Профилирование</span><span class="sxs-lookup"><span data-stu-id="fb277-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
- [<span data-ttu-id="fb277-130">Метод GetModuleInfo2</span><span class="sxs-lookup"><span data-stu-id="fb277-130">GetModuleInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)
