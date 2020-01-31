---
title: Метод ICorProfilerInfo2::GetAppDomainStaticAddress
ms.date: 03/30/2017
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
ms.openlocfilehash: 05d8c44655d8670194035c336bd62ae5d53bfec3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862975"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="3236f-102">Метод ICorProfilerInfo2::GetAppDomainStaticAddress</span><span class="sxs-lookup"><span data-stu-id="3236f-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="3236f-103">Возвращает адрес указанного поля статического домена приложения, которое находится в области заданного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="3236f-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3236f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3236f-104">Syntax</span></span>  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3236f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3236f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3236f-106">окне Идентификатор класса, который содержит запрошенное статическое поле домена приложения.</span><span class="sxs-lookup"><span data-stu-id="3236f-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="3236f-107">окне Токен метаданных для запрошенного статического поля домена приложения.</span><span class="sxs-lookup"><span data-stu-id="3236f-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="3236f-108">окне Идентификатор домена приложения, который является областью для запрошенного статического поля.</span><span class="sxs-lookup"><span data-stu-id="3236f-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="3236f-109">заполняет Указатель на адрес статического поля в пределах указанного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="3236f-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3236f-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="3236f-110">Remarks</span></span>  
 <span data-ttu-id="3236f-111">Метод `GetAppDomainStaticAddress` может возвращать одно из следующих данных:</span><span class="sxs-lookup"><span data-stu-id="3236f-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="3236f-112">CORPROF_E_DATAINCOMPLETE HRESULT, если заданному статическому полю не назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="3236f-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="3236f-113">Адреса объектов, которые могут находиться в куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3236f-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="3236f-114">Эти адреса могут стать недействительными после сборки мусора, поэтому после сборки мусора профилировщики не должны считать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="3236f-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="3236f-115">Перед завершением конструктора класса класса `GetAppDomainStaticAddress` будет возвращать CORPROF_E_DATAINCOMPLETE для всех его статических полей, хотя некоторые статические поля уже могут быть инициализированы и корневыми объектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3236f-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3236f-116">Требования</span><span class="sxs-lookup"><span data-stu-id="3236f-116">Requirements</span></span>  
 <span data-ttu-id="3236f-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3236f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3236f-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3236f-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3236f-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3236f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3236f-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3236f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3236f-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="3236f-121">See also</span></span>

- [<span data-ttu-id="3236f-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="3236f-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="3236f-123">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="3236f-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
