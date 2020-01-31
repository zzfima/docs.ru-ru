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
ms.openlocfilehash: e3d167be9a4091ae57a3283424186142e90ca7a1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868555"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="09820-102">Метод ICorProfilerInfo3::GetRuntimeInformation</span><span class="sxs-lookup"><span data-stu-id="09820-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="09820-103">Предоставляет сведения о версии для профилирования среды CLR.</span><span class="sxs-lookup"><span data-stu-id="09820-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09820-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09820-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="09820-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="09820-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="09820-106">заполняет Репрезентативный идентификатор выполняющегося экземпляра среды CLR в процессе.</span><span class="sxs-lookup"><span data-stu-id="09820-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="09820-107">Это то же самое, что `ClrInstanceID`, что отчеты о событиях запуска трассировки событий Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="09820-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="09820-108">заполняет Тип среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="09820-108">[out] The runtime type.</span></span> <span data-ttu-id="09820-109">Этот параметр возвращает `COR_PRF_DESKTOP_CLR` для классической версии среды CLR или `COR_PRF_CORE_CLR` для основной версии среды CLR, используемой в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="09820-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="09820-110">заполняет Основной номер версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="09820-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="09820-111">заполняет Дополнительный номер версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="09820-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="09820-112">заполняет Номер версии сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="09820-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="09820-113">заполняет Номер версии среды CLR, связанной с обновлением программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="09820-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="09820-114">окне Длина (в символах) буфера, на который `szVersionString` указывает.</span><span class="sxs-lookup"><span data-stu-id="09820-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="09820-115">заполняет Длина `szVersionString`в символах.</span><span class="sxs-lookup"><span data-stu-id="09820-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="09820-116">заполняет Строка версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="09820-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09820-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="09820-117">Remarks</span></span>  
 <span data-ttu-id="09820-118">Вы можете передать значение NULL для любого параметра.</span><span class="sxs-lookup"><span data-stu-id="09820-118">You may pass null for any parameter.</span></span> <span data-ttu-id="09820-119">Однако `pcchVersionString` не может иметь значение null, если `szVersionString` также не имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="09820-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09820-120">Требования</span><span class="sxs-lookup"><span data-stu-id="09820-120">Requirements</span></span>  
 <span data-ttu-id="09820-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09820-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09820-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09820-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09820-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09820-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09820-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09820-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09820-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="09820-125">See also</span></span>

- [<span data-ttu-id="09820-126">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="09820-126">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="09820-127">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="09820-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="09820-128">Профилирование</span><span class="sxs-lookup"><span data-stu-id="09820-128">Profiling</span></span>](index.md)
