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
ms.openlocfilehash: d5d7da343148d5f1c2aa9b2b639b094f8269199b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433202"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="3ee80-102">Метод ICorProfilerInfo2::GetContextStaticAddress</span><span class="sxs-lookup"><span data-stu-id="3ee80-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="3ee80-103">Возвращает адрес для указанного статического поля контекста, которое находится в области заданного контекста.</span><span class="sxs-lookup"><span data-stu-id="3ee80-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ee80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ee80-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ee80-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3ee80-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3ee80-106">окне Идентификатор класса, содержащего запрошенное статическое поле контекста.</span><span class="sxs-lookup"><span data-stu-id="3ee80-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="3ee80-107">окне Токен метаданных для запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="3ee80-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="3ee80-108">окне Идентификатор контекста, который является областью для запрошенного статического поля контекста.</span><span class="sxs-lookup"><span data-stu-id="3ee80-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="3ee80-109">заполняет Указатель на адрес статического поля в заданном контексте.</span><span class="sxs-lookup"><span data-stu-id="3ee80-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ee80-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ee80-110">Remarks</span></span>  
 <span data-ttu-id="3ee80-111">Метод `GetContextStaticAddress` может возвращать одно из следующих данных:</span><span class="sxs-lookup"><span data-stu-id="3ee80-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="3ee80-112">CORPROF_E_DATAINCOMPLETE HRESULT, если заданному статическому полю не назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="3ee80-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="3ee80-113">Адреса объектов, которые могут находиться в куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3ee80-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="3ee80-114">Эти адреса могут стать недействительными после сборки мусора, поэтому после сборки мусора профилировщики не должны считать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="3ee80-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="3ee80-115">Перед завершением конструктора класса класса `GetContextStaticAddress` будет возвращать CORPROF_E_DATAINCOMPLETE для всех его статических полей, хотя некоторые статические поля уже могут быть инициализированы и корневыми объектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3ee80-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ee80-116">Требования</span><span class="sxs-lookup"><span data-stu-id="3ee80-116">Requirements</span></span>  
 <span data-ttu-id="3ee80-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ee80-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ee80-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ee80-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ee80-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ee80-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ee80-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ee80-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ee80-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3ee80-121">See also</span></span>

- [<span data-ttu-id="3ee80-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="3ee80-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="3ee80-123">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="3ee80-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
