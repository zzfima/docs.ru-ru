---
title: Метод ICorProfilerInfo2::GetRVAStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
ms.openlocfilehash: ca64d4f5932fb4a0c0486fee5ca1017a6d3adaf2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868633"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="5b488-102">Метод ICorProfilerInfo2::GetRVAStaticAddress</span><span class="sxs-lookup"><span data-stu-id="5b488-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="5b488-103">Возвращает адрес указанного статического поля с относительным виртуальным адресом (RVA).</span><span class="sxs-lookup"><span data-stu-id="5b488-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b488-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b488-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b488-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b488-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="5b488-106">окне Идентификатор класса, содержащего запрошенное статическое поле для параметра RVA.</span><span class="sxs-lookup"><span data-stu-id="5b488-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="5b488-107">окне Токен метаданных для запрошенного статического поля.</span><span class="sxs-lookup"><span data-stu-id="5b488-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="5b488-108">заполняет Указатель на адрес поля static-RVA.</span><span class="sxs-lookup"><span data-stu-id="5b488-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b488-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="5b488-109">Remarks</span></span>  
 <span data-ttu-id="5b488-110">Метод `GetRVAStaticAddress` может возвращать одно из следующих данных:</span><span class="sxs-lookup"><span data-stu-id="5b488-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="5b488-111">CORPROF_E_DATAINCOMPLETE HRESULT, если заданному статическому полю не назначен адрес в указанном контексте.</span><span class="sxs-lookup"><span data-stu-id="5b488-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="5b488-112">Адреса объектов, которые могут находиться в куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="5b488-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="5b488-113">Эти адреса могут стать недействительными после сборки мусора, поэтому после сборки мусора профилировщики не должны считать, что они являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="5b488-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="5b488-114">Перед завершением конструктора класса класса `GetRVAStaticAddress` будет возвращать CORPROF_E_DATAINCOMPLETE для всех его статических полей, хотя некоторые статические поля уже могут быть инициализированы и могут быть корневыми объектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="5b488-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b488-115">Требования</span><span class="sxs-lookup"><span data-stu-id="5b488-115">Requirements</span></span>  
 <span data-ttu-id="5b488-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b488-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b488-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b488-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b488-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b488-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b488-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b488-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b488-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5b488-120">See also</span></span>

- [<span data-ttu-id="5b488-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5b488-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="5b488-122">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="5b488-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
