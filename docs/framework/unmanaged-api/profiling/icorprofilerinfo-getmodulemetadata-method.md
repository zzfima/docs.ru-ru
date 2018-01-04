---
title: "Метод ICorProfilerInfo::GetModuleMetaData"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetModuleMetaData
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ad52460bcd6eb320e970cd0ce2078f2e93df353
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="15ccc-102">Метод ICorProfilerInfo::GetModuleMetaData</span><span class="sxs-lookup"><span data-stu-id="15ccc-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="15ccc-103">Получает экземпляр интерфейса метаданных, сопоставляемый с указанным модулем.</span><span class="sxs-lookup"><span data-stu-id="15ccc-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ccc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15ccc-104">Syntax</span></span>  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15ccc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15ccc-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="15ccc-106">[in] Идентификатор модуля, с которым сопоставлен экземпляр интерфейса.</span><span class="sxs-lookup"><span data-stu-id="15ccc-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="15ccc-107">[in] Значение [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) перечисления, указывающее режим для открытия файлов манифеста.</span><span class="sxs-lookup"><span data-stu-id="15ccc-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="15ccc-108">Только `ofRead`, `ofWrite` и `ofNoTransform` bits являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="15ccc-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="15ccc-109">[in] Ссылка идентификатор (GUID) интерфейс метаданных, экземпляр которого будут извлечены.</span><span class="sxs-lookup"><span data-stu-id="15ccc-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="15ccc-110">В разделе [интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) список интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="15ccc-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="15ccc-111">[out] Указатель на адрес объекта интерфейса экземпляра метаданных.</span><span class="sxs-lookup"><span data-stu-id="15ccc-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15ccc-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="15ccc-112">Remarks</span></span>  
 <span data-ttu-id="15ccc-113">Существует возможность запросить метаданные для открытия в режиме чтения и записи, но это приведет к замедлению выполнения программы, поскольку изменения метаданных не может быть оптимизирован, как компилятор.</span><span class="sxs-lookup"><span data-stu-id="15ccc-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="15ccc-114">Некоторые модули (например, модули ресурсов) имеют без метаданных.</span><span class="sxs-lookup"><span data-stu-id="15ccc-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="15ccc-115">В таких случаях `GetModuleMetaData` возвратит значение HRESULT S_FALSE и null в *`ppOut`.</span><span class="sxs-lookup"><span data-stu-id="15ccc-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in *`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ccc-116">Требования</span><span class="sxs-lookup"><span data-stu-id="15ccc-116">Requirements</span></span>  
 <span data-ttu-id="15ccc-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15ccc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ccc-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15ccc-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="15ccc-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15ccc-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15ccc-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15ccc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ccc-121">См. также</span><span class="sxs-lookup"><span data-stu-id="15ccc-121">See Also</span></span>  
 [<span data-ttu-id="15ccc-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="15ccc-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
