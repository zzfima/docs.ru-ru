---
title: "Метод ICorProfilerInfo2::GetAppDomainStaticAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetAppDomainStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type: apiref
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf82d20085137e8ac55cf864a21260222fd6b514
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="269ba-102">Метод ICorProfilerInfo2::GetAppDomainStaticAddress</span><span class="sxs-lookup"><span data-stu-id="269ba-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="269ba-103">Получает адрес поля статического домена указанное приложение, которое находится в области указанного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="269ba-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="269ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="269ba-104">Syntax</span></span>  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="269ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="269ba-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="269ba-106">[in] Идентификатор класса для класса, содержащего поля статического домена запрошенное приложение.</span><span class="sxs-lookup"><span data-stu-id="269ba-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="269ba-107">[in] Токен метаданных для запрошенного приложения статического поля домена.</span><span class="sxs-lookup"><span data-stu-id="269ba-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="269ba-108">[in] Идентификатор домена приложения, который является областью для запрошенного статического поля.</span><span class="sxs-lookup"><span data-stu-id="269ba-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="269ba-109">[out] Указатель на адрес статического поля в пределах указанного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="269ba-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="269ba-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="269ba-110">Remarks</span></span>  
 <span data-ttu-id="269ba-111">`GetAppDomainStaticAddress` Метод может возвращать одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="269ba-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="269ba-112">CORPROF_E_DATAINCOMPLETE HRESULT, если заданного статического поля не был назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="269ba-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="269ba-113">Адреса объектов, которые могут находиться в куче сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="269ba-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="269ba-114">Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора профилировщики не следует предполагать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="269ba-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="269ba-115">До завершения конструктора класса `GetAppDomainStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, хотя некоторые статические поля уже могут быть инициализированы и болея объекты сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="269ba-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="269ba-116">Требования</span><span class="sxs-lookup"><span data-stu-id="269ba-116">Requirements</span></span>  
 <span data-ttu-id="269ba-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="269ba-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="269ba-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="269ba-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="269ba-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="269ba-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="269ba-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="269ba-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269ba-121">См. также</span><span class="sxs-lookup"><span data-stu-id="269ba-121">See Also</span></span>  
 [<span data-ttu-id="269ba-122">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="269ba-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="269ba-123">ICorProfilerInfo2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="269ba-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
