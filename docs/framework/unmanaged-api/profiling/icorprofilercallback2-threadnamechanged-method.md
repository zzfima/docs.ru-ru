---
title: Метод ICorProfilerCallback2::ThreadNameChanged
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
ms.openlocfilehash: c5182fd44f0cc2ad7b836bbcbddc469c89dbacb7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865705"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="7dc9a-102">Метод ICorProfilerCallback2::ThreadNameChanged</span><span class="sxs-lookup"><span data-stu-id="7dc9a-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="7dc9a-103">Уведомляет профилировщик кода о том, что имя потока изменилось.</span><span class="sxs-lookup"><span data-stu-id="7dc9a-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dc9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7dc9a-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dc9a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7dc9a-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="7dc9a-106">окне Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="7dc9a-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="7dc9a-107">окне Длина нового имени потока.</span><span class="sxs-lookup"><span data-stu-id="7dc9a-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="7dc9a-108">окне Новое имя потока.</span><span class="sxs-lookup"><span data-stu-id="7dc9a-108">[in] The new name of the thread.</span></span> <span data-ttu-id="7dc9a-109">Имя не завершается нулем.</span><span class="sxs-lookup"><span data-stu-id="7dc9a-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dc9a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7dc9a-110">Requirements</span></span>  
 <span data-ttu-id="7dc9a-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dc9a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dc9a-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7dc9a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7dc9a-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dc9a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7dc9a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dc9a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc9a-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="7dc9a-115">See also</span></span>

- [<span data-ttu-id="7dc9a-116">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7dc9a-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7dc9a-117">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="7dc9a-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
