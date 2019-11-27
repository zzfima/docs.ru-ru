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
ms.openlocfilehash: e2a4df262e076c960640977bea0d22be19802140
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449666"
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a><span data-ttu-id="79c39-102">Метод ICorProfilerInfo3::GetModuleInfo2</span><span class="sxs-lookup"><span data-stu-id="79c39-102">ICorProfilerInfo3::GetModuleInfo2 Method</span></span>
<span data-ttu-id="79c39-103">Возвращает имя файла модуля, идентификатор родительской сборки модуля и битовую маску, описывающую свойства модуля, по идентификатору модуля.</span><span class="sxs-lookup"><span data-stu-id="79c39-103">Given a module ID, returns the file name of the module, the ID of the module's parent assembly, and a bitmask that describes the properties of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79c39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79c39-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="79c39-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79c39-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="79c39-106">[in] Идентификатор модуля, для которого будут извлекаться сведения.</span><span class="sxs-lookup"><span data-stu-id="79c39-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="79c39-107">[out] Базовый адрес, по которому модуль был загружен.</span><span class="sxs-lookup"><span data-stu-id="79c39-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="79c39-108">[in] Длина буфера возврата `szName` в символах.</span><span class="sxs-lookup"><span data-stu-id="79c39-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="79c39-109">[out] Указатель на общую длину возвращаемого имени файла модуля в символах.</span><span class="sxs-lookup"><span data-stu-id="79c39-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="79c39-110">[out] Буфер расширенных символов, предоставленный вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="79c39-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="79c39-111">При возврате метода этот буфер содержит имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="79c39-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="79c39-112">[out] Указатель на идентификатор родительской сборки модуля.</span><span class="sxs-lookup"><span data-stu-id="79c39-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
 `pdwModuleFlags`  
 <span data-ttu-id="79c39-113">заполняет Битовая маска значений из перечисления [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) , определяющая свойства модуля.</span><span class="sxs-lookup"><span data-stu-id="79c39-113">[out] A bitmask of values from the [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) enumeration that specify the properties of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79c39-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="79c39-114">Remarks</span></span>  
 <span data-ttu-id="79c39-115">Для динамических модулей параметр `szName` является именем метаданных модуля, а базовый адрес равен 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="79c39-115">For dynamic modules, the `szName` parameter is the metadata name of the module, and the base address is 0 (zero).</span></span> <span data-ttu-id="79c39-116">Имя метаданных — это значение в столбце Name таблицы Module в метаданных.</span><span class="sxs-lookup"><span data-stu-id="79c39-116">The metadata name is the value in the Name column from the Module table inside metadata.</span></span> <span data-ttu-id="79c39-117">Это также предоставляется в качестве свойства <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> для управляемого кода, а также в качестве параметра `szName` метода [IMetaDataImport:: жетскопепропс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) в неуправляемый клиентский код метаданных.</span><span class="sxs-lookup"><span data-stu-id="79c39-117">This is also exposed as the <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> property to managed code, and as the `szName` parameter of the [IMetaDataImport::GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) method to unmanaged metadata client code.</span></span>  
  
 <span data-ttu-id="79c39-118">Несмотря на то, что метод `GetModuleInfo2` может вызываться сразу после существования идентификатора модуля, идентификатор родительской сборки будет недоступен до тех пор, пока профилировщик не получит обратный вызов [ICorProfilerCallback:: модулеаттачедтоассембли](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="79c39-118">Although the `GetModuleInfo2` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="79c39-119">После возврата метода `GetModuleInfo2` необходимо убедиться, что буфер `szName` был достаточно велик, чтобы вместить в себя полное имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="79c39-119">When `GetModuleInfo2` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="79c39-120">Для этого сравните значение, на которое указывает параметр `pcchName`, со значением параметра `cchName`.</span><span class="sxs-lookup"><span data-stu-id="79c39-120">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="79c39-121">Если параметр `pcchName` указывает на значение, превышающее значение `cchName`, выделите буфер `szName` большего размера, обновите параметр `cchName`, задав новый, больший размер, и вызовите метод `GetModuleInfo2` снова.</span><span class="sxs-lookup"><span data-stu-id="79c39-121">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo2` again.</span></span>  
  
 <span data-ttu-id="79c39-122">Кроме того, сначала можно вызвать метод `GetModuleInfo2` с буфером `szName` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="79c39-122">Alternatively, you can first call `GetModuleInfo2` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="79c39-123">Затем можно задать размер буфера равным значению, возвращенному в параметре `pcchName`, и вызвать метод `GetModuleInfo2` снова.</span><span class="sxs-lookup"><span data-stu-id="79c39-123">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79c39-124">Требования</span><span class="sxs-lookup"><span data-stu-id="79c39-124">Requirements</span></span>  
 <span data-ttu-id="79c39-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79c39-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79c39-126">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79c39-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79c39-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79c39-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79c39-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79c39-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79c39-129">См. также</span><span class="sxs-lookup"><span data-stu-id="79c39-129">See also</span></span>

- [<span data-ttu-id="79c39-130">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="79c39-130">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="79c39-131">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="79c39-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="79c39-132">Профилирование</span><span class="sxs-lookup"><span data-stu-id="79c39-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
