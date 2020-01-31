---
title: Метод ICorProfilerInfo2::GetContextStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
ms.openlocfilehash: d99e5000cdd0d7252764554025815dbace2289f4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868685"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="bfe3c-102">Метод ICorProfilerInfo2::GetContextStaticAddress</span><span class="sxs-lookup"><span data-stu-id="bfe3c-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="bfe3c-103">Возвращает адрес для указанного статического поля контекста, которое находится в области заданного контекста.</span><span class="sxs-lookup"><span data-stu-id="bfe3c-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe3c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfe3c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfe3c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bfe3c-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="bfe3c-106">окне Идентификатор класса, содержащего запрошенное статическое поле контекста.</span><span class="sxs-lookup"><span data-stu-id="bfe3c-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="bfe3c-107">окне Токен метаданных для запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="bfe3c-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="bfe3c-108">окне Идентификатор контекста, который является областью для запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="bfe3c-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="bfe3c-109">заполняет Указатель на адрес статического поля в заданном контексте.</span><span class="sxs-lookup"><span data-stu-id="bfe3c-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfe3c-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="bfe3c-110">Remarks</span></span>  
 <span data-ttu-id="bfe3c-111">Метод `GetContextStaticAddress` может возвращать одно из следующих данных:</span><span class="sxs-lookup"><span data-stu-id="bfe3c-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="bfe3c-112">CORPROF_E_DATAINCOMPLETE HRESULT, если заданному статическому полю не назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="bfe3c-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="bfe3c-113">Адреса объектов, которые могут находиться в куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bfe3c-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="bfe3c-114">Эти адреса могут стать недействительными после сборки мусора, поэтому после сборки мусора профилировщики не должны считать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="bfe3c-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="bfe3c-115">Перед завершением конструктора класса класса `GetContextStaticAddress` будет возвращать CORPROF_E_DATAINCOMPLETE для всех его статических полей, хотя некоторые статические поля уже могут быть инициализированы и корневыми объектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bfe3c-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfe3c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="bfe3c-116">Requirements</span></span>  
 <span data-ttu-id="bfe3c-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfe3c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfe3c-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bfe3c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bfe3c-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfe3c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfe3c-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfe3c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe3c-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="bfe3c-121">See also</span></span>

- [<span data-ttu-id="bfe3c-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="bfe3c-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="bfe3c-123">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="bfe3c-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
