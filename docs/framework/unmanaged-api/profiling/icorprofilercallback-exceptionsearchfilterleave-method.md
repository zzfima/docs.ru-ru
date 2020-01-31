---
title: Метод ICorProfilerCallback::ExceptionSearchFilterLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
ms.openlocfilehash: 607143d7848534329a55a9caebdb6b9175b2749c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866420"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="919d1-102">Метод ICorProfilerCallback::ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="919d1-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="919d1-103">Уведомляет профилировщик о завершении выполнения пользовательского фильтра.</span><span class="sxs-lookup"><span data-stu-id="919d1-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="919d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="919d1-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="919d1-105">Требования</span><span class="sxs-lookup"><span data-stu-id="919d1-105">Requirements</span></span>  
 <span data-ttu-id="919d1-106">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="919d1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="919d1-107">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="919d1-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="919d1-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="919d1-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="919d1-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="919d1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="919d1-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="919d1-110">See also</span></span>

- [<span data-ttu-id="919d1-111">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="919d1-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="919d1-112">Метод ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="919d1-112">ExceptionSearchFilterEnter Method</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)
