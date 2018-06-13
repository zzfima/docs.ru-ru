---
title: Метод ICorProfilerInfo2::GetThreadStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a38c8323157cee866ac0ecab97532b9b72a932b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454132"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="345ac-102">Метод ICorProfilerInfo2::GetThreadStaticAddress</span><span class="sxs-lookup"><span data-stu-id="345ac-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="345ac-103">Возвращает адрес указанного поля статического потока, которое находится в области действия заданного потока.</span><span class="sxs-lookup"><span data-stu-id="345ac-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="345ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="345ac-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="345ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="345ac-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="345ac-106">[in] Идентификатор класса, содержащего запрошенного поля статического потока.</span><span class="sxs-lookup"><span data-stu-id="345ac-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="345ac-107">[in] Токен метаданных для запрошенного поля статического потока.</span><span class="sxs-lookup"><span data-stu-id="345ac-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="345ac-108">[in] Идентификатор потока, который является областью для запрошенного статического поля.</span><span class="sxs-lookup"><span data-stu-id="345ac-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="345ac-109">[out] Указатель на адрес статического поля, которое находится в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="345ac-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="345ac-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="345ac-110">Remarks</span></span>  
 <span data-ttu-id="345ac-111">`GetThreadStaticAddress` Метод может возвращать одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="345ac-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="345ac-112">CORPROF_E_DATAINCOMPLETE HRESULT, если заданного статического поля не был назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="345ac-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="345ac-113">Адреса объектов, которые могут находиться в куче сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="345ac-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="345ac-114">Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора коллекции профилировщики не должны предполагать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="345ac-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="345ac-115">До завершения конструктора класса `GetThreadStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, хотя некоторые статические поля уже могут быть инициализированы и болея объекты сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="345ac-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="345ac-116">Требования</span><span class="sxs-lookup"><span data-stu-id="345ac-116">Requirements</span></span>  
 <span data-ttu-id="345ac-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="345ac-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="345ac-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="345ac-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="345ac-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="345ac-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="345ac-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="345ac-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="345ac-121">См. также</span><span class="sxs-lookup"><span data-stu-id="345ac-121">See Also</span></span>  
 [<span data-ttu-id="345ac-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="345ac-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="345ac-123">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="345ac-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
