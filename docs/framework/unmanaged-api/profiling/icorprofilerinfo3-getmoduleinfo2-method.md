---
title: Метод ICorProfilerInfo3::GetModuleInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetModuleInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetModuleInfo2
helpviewer_keywords:
- ICorProfilerInfo3::GetModuleInfo2 method [.NET Framework profiling]
- GetModuleInfo2 method [.NET Framework profiling]
ms.assetid: f1f6b8f3-dcfc-49e8-be76-ea50ea90d5a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fadca931ca4a57c83257f24e34e847870c9f493
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107488"
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a><span data-ttu-id="5c781-102">Метод ICorProfilerInfo3::GetModuleInfo2</span><span class="sxs-lookup"><span data-stu-id="5c781-102">ICorProfilerInfo3::GetModuleInfo2 Method</span></span>
<span data-ttu-id="5c781-103">Возвращает имя файла модуля, идентификатор родительской сборки модуля и битовую маску, описывающую свойства модуля, по идентификатору модуля.</span><span class="sxs-lookup"><span data-stu-id="5c781-103">Given a module ID, returns the file name of the module, the ID of the module's parent assembly, and a bitmask that describes the properties of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c781-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c781-104">Syntax</span></span>  
  
```  
HRESULT GetModuleInfo2(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, annotation("__out_ecount_part(cchName, *pcchName)")]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
    [out] DWORD                 *pdwModuleFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c781-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c781-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="5c781-106">[in] Идентификатор модуля, для которого будут извлекаться сведения.</span><span class="sxs-lookup"><span data-stu-id="5c781-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="5c781-107">[out] Базовый адрес, по которому модуль был загружен.</span><span class="sxs-lookup"><span data-stu-id="5c781-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5c781-108">[in] Длина буфера возврата `szName` в символах.</span><span class="sxs-lookup"><span data-stu-id="5c781-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5c781-109">[out] Указатель на общую длину возвращаемого имени файла модуля в символах.</span><span class="sxs-lookup"><span data-stu-id="5c781-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="5c781-110">[out] Буфер расширенных символов, предоставленный вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="5c781-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="5c781-111">При возврате метода этот буфер содержит имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="5c781-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="5c781-112">[out] Указатель на идентификатор родительской сборки модуля.</span><span class="sxs-lookup"><span data-stu-id="5c781-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
 `pdwModuleFlags`  
 <span data-ttu-id="5c781-113">[out] Битовая маска значений из [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) перечисления, указывающего свойства модуля.</span><span class="sxs-lookup"><span data-stu-id="5c781-113">[out] A bitmask of values from the [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) enumeration that specify the properties of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c781-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c781-114">Remarks</span></span>  
 <span data-ttu-id="5c781-115">Для динамических модулей параметр `szName` является именем метаданных модуля, а базовый адрес равен 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="5c781-115">For dynamic modules, the `szName` parameter is the metadata name of the module, and the base address is 0 (zero).</span></span> <span data-ttu-id="5c781-116">Имя метаданных — это значение в столбце Name таблицы Module в метаданных.</span><span class="sxs-lookup"><span data-stu-id="5c781-116">The metadata name is the value in the Name column from the Module table inside metadata.</span></span> <span data-ttu-id="5c781-117">Это также доступно в виде <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> свойство в управляемый код и как `szName` параметр [IMetaDataImport::GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) метод в клиентский код неуправляемых метаданных.</span><span class="sxs-lookup"><span data-stu-id="5c781-117">This is also exposed as the <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> property to managed code, and as the `szName` parameter of the [IMetaDataImport::GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) method to unmanaged metadata client code.</span></span>  
  
 <span data-ttu-id="5c781-118">Несмотря на то что `GetModuleInfo2` метод может вызываться сразу же существует идентификатор модуля, идентификатор родительской сборки будет недоступен до получения профилировщиком [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="5c781-118">Although the `GetModuleInfo2` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="5c781-119">После возврата метода `GetModuleInfo2` необходимо убедиться, что буфер `szName` был достаточно велик, чтобы вместить в себя полное имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="5c781-119">When `GetModuleInfo2` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="5c781-120">Для этого сравните значение, на которое указывает параметр `pcchName`, со значением параметра `cchName`.</span><span class="sxs-lookup"><span data-stu-id="5c781-120">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="5c781-121">Если параметр `pcchName` указывает на значение, превышающее значение `cchName`, выделите буфер `szName` большего размера, обновите параметр `cchName`, задав новый, больший размер, и вызовите метод `GetModuleInfo2` снова.</span><span class="sxs-lookup"><span data-stu-id="5c781-121">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo2` again.</span></span>  
  
 <span data-ttu-id="5c781-122">Кроме того, сначала можно вызвать метод `GetModuleInfo2` с буфером `szName` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="5c781-122">Alternatively, you can first call `GetModuleInfo2` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="5c781-123">Затем можно задать размер буфера равным значению, возвращенному в параметре `pcchName`, и вызвать метод `GetModuleInfo2` снова.</span><span class="sxs-lookup"><span data-stu-id="5c781-123">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c781-124">Требования</span><span class="sxs-lookup"><span data-stu-id="5c781-124">Requirements</span></span>  
 <span data-ttu-id="5c781-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c781-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c781-126">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c781-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c781-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c781-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c781-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c781-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c781-129">См. также</span><span class="sxs-lookup"><span data-stu-id="5c781-129">See also</span></span>

- [<span data-ttu-id="5c781-130">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5c781-130">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="5c781-131">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="5c781-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5c781-132">Профилирование</span><span class="sxs-lookup"><span data-stu-id="5c781-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
