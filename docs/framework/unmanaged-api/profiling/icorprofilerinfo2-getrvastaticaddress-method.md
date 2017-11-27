---
title: "Метод ICorProfilerInfo2::GetRVAStaticAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetRVAStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type: apiref
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64553e8f611a8111aaaf9ababd1a7556f1192740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="3234a-102">Метод ICorProfilerInfo2::GetRVAStaticAddress</span><span class="sxs-lookup"><span data-stu-id="3234a-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="3234a-103">Возвращает адрес указанного относительного виртуального адреса (RVA) статического поля.</span><span class="sxs-lookup"><span data-stu-id="3234a-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3234a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3234a-104">Syntax</span></span>  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3234a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3234a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3234a-106">[in] Идентификатор класса, содержащего запрашиваемого RVA статического поля.</span><span class="sxs-lookup"><span data-stu-id="3234a-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="3234a-107">[in] Токен метаданных для запрошенного RVA статического поля.</span><span class="sxs-lookup"><span data-stu-id="3234a-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="3234a-108">[out] Указатель на адрес RVA статического поля.</span><span class="sxs-lookup"><span data-stu-id="3234a-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3234a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3234a-109">Remarks</span></span>  
 <span data-ttu-id="3234a-110">`GetRVAStaticAddress` Метод может возвращать одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="3234a-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="3234a-111">CORPROF_E_DATAINCOMPLETE HRESULT, если заданного статического поля не был назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="3234a-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="3234a-112">Адреса объектов, которые могут находиться в куче сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="3234a-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="3234a-113">Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора профилировщики не следует предполагать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="3234a-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="3234a-114">До завершения конструктора класса `GetRVAStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, хотя некоторые статические поля уже могут быть инициализированы и могут маршрутизировать объекты сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3234a-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3234a-115">Требования</span><span class="sxs-lookup"><span data-stu-id="3234a-115">Requirements</span></span>  
 <span data-ttu-id="3234a-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3234a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3234a-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3234a-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3234a-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3234a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3234a-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3234a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3234a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="3234a-120">See Also</span></span>  
 [<span data-ttu-id="3234a-121">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3234a-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="3234a-122">ICorProfilerInfo2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3234a-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
