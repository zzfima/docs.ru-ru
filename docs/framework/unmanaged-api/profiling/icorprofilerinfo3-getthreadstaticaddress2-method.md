---
title: Метод ICorProfilerInfo3::GetThreadStaticAddress2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
ms.openlocfilehash: ee44c89ec30edcb6233081f0757fa0f7b7191178
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449648"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="b4c58-102">Метод ICorProfilerInfo3::GetThreadStaticAddress2</span><span class="sxs-lookup"><span data-stu-id="b4c58-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>
<span data-ttu-id="b4c58-103">Возвращает адрес указанного поля статического потока, которое находится в области действия заданного потока и домена приложения.</span><span class="sxs-lookup"><span data-stu-id="b4c58-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c58-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4c58-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4c58-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4c58-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="b4c58-106">окне Идентификатор класса, содержащего запрошенное статическое поле потока.</span><span class="sxs-lookup"><span data-stu-id="b4c58-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="b4c58-107">окне Токен метаданных для запрошенного статического поля потока.</span><span class="sxs-lookup"><span data-stu-id="b4c58-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="b4c58-108">[in] Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="b4c58-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="b4c58-109">окне Идентификатор потока, который является областью для запрошенного статического поля.</span><span class="sxs-lookup"><span data-stu-id="b4c58-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="b4c58-110">заполняет Указатель на адрес статического поля, находящихся в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="b4c58-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4c58-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4c58-111">Remarks</span></span>  
 <span data-ttu-id="b4c58-112">Метод `GetThreadStaticAddress2` может возвращать одно из следующих данных:</span><span class="sxs-lookup"><span data-stu-id="b4c58-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
- <span data-ttu-id="b4c58-113">CORPROF_E_DATAINCOMPLETE HRESULT, если заданному статическому полю не назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="b4c58-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="b4c58-114">Адреса объектов, которые могут находиться в куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b4c58-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="b4c58-115">Эти адреса могут стать недействительными после сборки мусора, поэтому после сборки мусора профилировщики не должны считать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="b4c58-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="b4c58-116">Перед завершением конструктора класса класса `GetThreadStaticAddress2` будет возвращать CORPROF_E_DATAINCOMPLETE для всех его статических полей, хотя некоторые статические поля уже могут быть инициализированы и корневыми объектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b4c58-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="b4c58-117">Метод [ICorProfilerInfo2:: жетсреадстатикаддресс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) аналогичен методу `GetThreadStaticAddress2`, но не принимает аргумент домена приложения.</span><span class="sxs-lookup"><span data-stu-id="b4c58-117">The [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4c58-118">Требования</span><span class="sxs-lookup"><span data-stu-id="b4c58-118">Requirements</span></span>  
 <span data-ttu-id="b4c58-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4c58-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4c58-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b4c58-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b4c58-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4c58-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4c58-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4c58-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c58-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b4c58-123">See also</span></span>

- [<span data-ttu-id="b4c58-124">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="b4c58-124">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b4c58-125">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="b4c58-125">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b4c58-126">Профилирование</span><span class="sxs-lookup"><span data-stu-id="b4c58-126">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
