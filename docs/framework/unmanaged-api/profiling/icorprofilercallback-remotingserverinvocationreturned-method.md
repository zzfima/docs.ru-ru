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
ms.openlocfilehash: 00f5fd44d340a76200537871a9860f67601b66d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208713"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="1d625-102">Метод ICorProfilerCallback::RemotingServerInvocationReturned</span><span class="sxs-lookup"><span data-stu-id="1d625-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="1d625-103">Уведомляет профилировщик, что процесс завершен вызов метода в ответ на запрос вызова удаленного метода.</span><span class="sxs-lookup"><span data-stu-id="1d625-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d625-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d625-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="1d625-105">Требования</span><span class="sxs-lookup"><span data-stu-id="1d625-105">Requirements</span></span>  
 <span data-ttu-id="1d625-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d625-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d625-107">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d625-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d625-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d625-108">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1d625-109">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1d625-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1d625-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1d625-110">See also</span></span>

- [<span data-ttu-id="1d625-111">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1d625-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
