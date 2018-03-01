---
title: "Метод ICorProfilerInfo2::GetAppDomainStaticAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2fad6cccc3992f001780bf8bd1a4c879dc6aa754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="05b8f-102">Метод ICorProfilerInfo2::GetAppDomainStaticAddress</span><span class="sxs-lookup"><span data-stu-id="05b8f-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="05b8f-103">Получает адрес поля статического домена указанное приложение, которое находится в области указанного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="05b8f-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05b8f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05b8f-104">Syntax</span></span>  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05b8f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="05b8f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="05b8f-106">[in] Идентификатор класса для класса, содержащего поля статического домена запрошенное приложение.</span><span class="sxs-lookup"><span data-stu-id="05b8f-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="05b8f-107">[in] Токен метаданных для запрошенного приложения статического поля домена.</span><span class="sxs-lookup"><span data-stu-id="05b8f-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="05b8f-108">[in] Идентификатор домена приложения, который является областью для запрошенного статического поля.</span><span class="sxs-lookup"><span data-stu-id="05b8f-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="05b8f-109">[out] Указатель на адрес статического поля в пределах указанного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="05b8f-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05b8f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="05b8f-110">Remarks</span></span>  
 <span data-ttu-id="05b8f-111">`GetAppDomainStaticAddress` Метод может возвращать одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="05b8f-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="05b8f-112">CORPROF_E_DATAINCOMPLETE HRESULT, если заданного статического поля не был назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="05b8f-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="05b8f-113">Адреса объектов, которые могут находиться в куче сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="05b8f-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="05b8f-114">Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора профилировщики не следует предполагать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="05b8f-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="05b8f-115">До завершения конструктора класса `GetAppDomainStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, хотя некоторые статические поля уже могут быть инициализированы и болея объекты сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="05b8f-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05b8f-116">Требования</span><span class="sxs-lookup"><span data-stu-id="05b8f-116">Requirements</span></span>  
 <span data-ttu-id="05b8f-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05b8f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05b8f-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="05b8f-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="05b8f-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05b8f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05b8f-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05b8f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05b8f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="05b8f-121">See Also</span></span>  
 [<span data-ttu-id="05b8f-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="05b8f-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="05b8f-123">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="05b8f-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
