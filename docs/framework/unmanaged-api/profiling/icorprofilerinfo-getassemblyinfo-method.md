---
title: Метод ICorProfilerInfo::GetAssemblyInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAssemblyInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type:
- apiref
ms.openlocfilehash: 1e08d246136b33ffaaea91367d428e0bf2db99c1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864132"
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a><span data-ttu-id="9ed6e-102">Метод ICorProfilerInfo::GetAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="9ed6e-102">ICorProfilerInfo::GetAssemblyInfo Method</span></span>
<span data-ttu-id="9ed6e-103">Принимает идентификатор сборки и возвращает имя сборки, а также идентификатор ее модуля манифеста.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-103">Accepts an assembly ID, and returns the assembly's name and the ID of its manifest module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ed6e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ed6e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ed6e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ed6e-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="9ed6e-106">[in] Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-106">[in] The identifier of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="9ed6e-107">[in] Длина `szName` в символах.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-107">[in] The length, in characters, of `szName`.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9ed6e-108">[out] Указатель на общую длину имени сборки в символах.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-108">[out] A pointer to the total character length of the assembly's name.</span></span>  
  
 `szName`  
 <span data-ttu-id="9ed6e-109">[out] Буфер расширенных символов, предоставленный вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-109">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="9ed6e-110">Когда функция возвращает значение, оно содержит имя сборки.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-110">When the function returns, it will contain the assembly's name.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="9ed6e-111">[out] Указатель на идентификатор домена приложения, содержащего эту сборку.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-111">[out] A pointer to the ID of the application domain that contains the assembly.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="9ed6e-112">[out] Указатель на идентификатор модуля манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-112">[out] A pointer to the ID of the assembly's manifest module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ed6e-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="9ed6e-113">Remarks</span></span>  
 <span data-ttu-id="9ed6e-114">После возврата этого метода необходимо убедиться, что буфер `szName` был достаточно велик, чтобы вместить в себя полное имя сборки.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the assembly.</span></span> <span data-ttu-id="9ed6e-115">Для этого сравните значение, на которое указывает параметр `pcchName`, со значением параметра `cchName`.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="9ed6e-116">Если параметр `pcchName` указывает на значение, превышающее значение `cchName`, выделите буфер `szName` большего размера, обновите параметр `cchName`, задав новый, больший размер, и вызовите метод `GetAssemblyInfo` снова.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAssemblyInfo` again.</span></span>  
  
 <span data-ttu-id="9ed6e-117">Кроме того, сначала можно вызвать метод `GetAssemblyInfo` с буфером `szName` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-117">Alternatively, you can first call `GetAssemblyInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="9ed6e-118">Затем можно настроить размер буфера, исходя из значения, возвращенного в `pcchName`, и вызвать метод `GetAssemblyInfo` снова.</span><span class="sxs-lookup"><span data-stu-id="9ed6e-118">You can then adjust the buffer size based on the value returned in `pcchName` and call `GetAssemblyInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ed6e-119">Требования</span><span class="sxs-lookup"><span data-stu-id="9ed6e-119">Requirements</span></span>  
 <span data-ttu-id="9ed6e-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ed6e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ed6e-121">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9ed6e-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ed6e-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ed6e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ed6e-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ed6e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed6e-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ed6e-124">See also</span></span>

- [<span data-ttu-id="9ed6e-125">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="9ed6e-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="9ed6e-126">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="9ed6e-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9ed6e-127">Профилирование</span><span class="sxs-lookup"><span data-stu-id="9ed6e-127">Profiling</span></span>](index.md)
