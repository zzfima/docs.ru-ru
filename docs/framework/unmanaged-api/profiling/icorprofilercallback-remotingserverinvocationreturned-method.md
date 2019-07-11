---
title: Метод ICorProfilerCallback::RemotingServerInvocationReturned
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationReturned
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned method [.NET Framework profiling]
- RemotingServerInvocationReturned method [.NET Framework profiling]
ms.assetid: a4de6805-e159-4280-99e5-3390c86166d0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 731907d69f3257306c536d73112300ffd5225538
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782895"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="761e1-102">Метод ICorProfilerCallback::RemotingServerInvocationReturned</span><span class="sxs-lookup"><span data-stu-id="761e1-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="761e1-103">Уведомляет профилировщик, что процесс завершен вызов метода в ответ на запрос вызова удаленного метода.</span><span class="sxs-lookup"><span data-stu-id="761e1-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="761e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="761e1-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="761e1-105">Требования</span><span class="sxs-lookup"><span data-stu-id="761e1-105">Requirements</span></span>  
 <span data-ttu-id="761e1-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="761e1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="761e1-107">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="761e1-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="761e1-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="761e1-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="761e1-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="761e1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="761e1-110">См. также</span><span class="sxs-lookup"><span data-stu-id="761e1-110">See also</span></span>

- [<span data-ttu-id="761e1-111">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="761e1-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
