---
title: Метод ICorProfilerInfo3::GetRuntimeInformation
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
ms.openlocfilehash: 20556d85655a0a1bbe069a94b99c19c774a13ce6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449682"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="6e8d1-102">Метод ICorProfilerInfo3::GetRuntimeInformation</span><span class="sxs-lookup"><span data-stu-id="6e8d1-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="6e8d1-103">Предоставляет сведения о версии для профилирования среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e8d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e8d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e8d1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e8d1-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="6e8d1-106">заполняет Репрезентативный идентификатор выполняющегося экземпляра среды CLR в процессе.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="6e8d1-107">Это то же самое, что `ClrInstanceID`, что отчеты о событиях запуска трассировки событий Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="6e8d1-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="6e8d1-108">заполняет Тип среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-108">[out] The runtime type.</span></span> <span data-ttu-id="6e8d1-109">Этот параметр возвращает `COR_PRF_DESKTOP_CLR` для классической версии среды CLR или `COR_PRF_CORE_CLR` для основной версии среды CLR, используемой в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="6e8d1-110">заполняет Основной номер версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="6e8d1-111">заполняет Дополнительный номер версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="6e8d1-112">заполняет Номер версии сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="6e8d1-113">заполняет Номер версии среды CLR, связанной с обновлением программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="6e8d1-114">окне Длина (в символах) буфера, на который `szVersionString` указывает.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="6e8d1-115">заполняет Длина `szVersionString`в символах.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="6e8d1-116">заполняет Строка версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e8d1-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="6e8d1-117">Remarks</span></span>  
 <span data-ttu-id="6e8d1-118">Вы можете передать значение NULL для любого параметра.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-118">You may pass null for any parameter.</span></span> <span data-ttu-id="6e8d1-119">Однако `pcchVersionString` не может иметь значение null, если `szVersionString` также не имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e8d1-120">Требования</span><span class="sxs-lookup"><span data-stu-id="6e8d1-120">Requirements</span></span>  
 <span data-ttu-id="6e8d1-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e8d1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e8d1-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6e8d1-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6e8d1-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e8d1-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e8d1-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e8d1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e8d1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6e8d1-125">See also</span></span>

- [<span data-ttu-id="6e8d1-126">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="6e8d1-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="6e8d1-127">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="6e8d1-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="6e8d1-128">Профилирование</span><span class="sxs-lookup"><span data-stu-id="6e8d1-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
