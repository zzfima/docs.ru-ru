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
ms.openlocfilehash: 2c98f67e20ea36d7fbbb31be2e3761594b674c36
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868607"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="ff5d6-102">Метод ICorProfilerInfo2::GetThreadStaticAddress</span><span class="sxs-lookup"><span data-stu-id="ff5d6-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="ff5d6-103">Возвращает адрес указанного статического поля потока, который находится в области заданного потока.</span><span class="sxs-lookup"><span data-stu-id="ff5d6-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff5d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff5d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff5d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff5d6-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ff5d6-106">окне Идентификатор класса, содержащего запрошенное статическое поле потока.</span><span class="sxs-lookup"><span data-stu-id="ff5d6-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="ff5d6-107">окне Токен метаданных для запрошенного статического поля потока.</span><span class="sxs-lookup"><span data-stu-id="ff5d6-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="ff5d6-108">окне Идентификатор потока, который является областью для запрошенного статического поля.</span><span class="sxs-lookup"><span data-stu-id="ff5d6-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="ff5d6-109">заполняет Указатель на адрес статического поля, находящихся в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="ff5d6-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff5d6-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="ff5d6-110">Remarks</span></span>  
 <span data-ttu-id="ff5d6-111">Метод `GetThreadStaticAddress` может возвращать одно из следующих данных:</span><span class="sxs-lookup"><span data-stu-id="ff5d6-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="ff5d6-112">CORPROF_E_DATAINCOMPLETE HRESULT, если заданному статическому полю не назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="ff5d6-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="ff5d6-113">Адреса объектов, которые могут находиться в куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ff5d6-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="ff5d6-114">Эти адреса могут стать недействительными после сборки мусора, поэтому после завершения профилирования сборщиком мусора не следует считать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="ff5d6-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="ff5d6-115">Перед завершением конструктора класса класса `GetThreadStaticAddress` будет возвращать CORPROF_E_DATAINCOMPLETE для всех его статических полей, хотя некоторые статические поля уже могут быть инициализированы и корневыми объектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ff5d6-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff5d6-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ff5d6-116">Requirements</span></span>  
 <span data-ttu-id="ff5d6-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff5d6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff5d6-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff5d6-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff5d6-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff5d6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff5d6-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff5d6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff5d6-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff5d6-121">See also</span></span>

- [<span data-ttu-id="ff5d6-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ff5d6-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="ff5d6-123">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="ff5d6-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
