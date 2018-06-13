---
title: Метод ICorProfilerCallback::RemotingClientInvocationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1dcb79c4130f6bd163cb807ff92b95db8360a185
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461972"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="8aff8-102">Метод ICorProfilerCallback::RemotingClientInvocationStarted</span><span class="sxs-lookup"><span data-stu-id="8aff8-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="8aff8-103">Уведомляет профилировщик о начале вызова удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="8aff8-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aff8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8aff8-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8aff8-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="8aff8-105">Remarks</span></span>  
 <span data-ttu-id="8aff8-106">Это событие является одинаковым для синхронные и асинхронные вызовы.</span><span class="sxs-lookup"><span data-stu-id="8aff8-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="8aff8-107">Каждая из следующих пар обратных вызовов произойдет в том же потоке.</span><span class="sxs-lookup"><span data-stu-id="8aff8-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="8aff8-108">`RemotingClientInvocationStarted` и [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="8aff8-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="8aff8-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) и [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="8aff8-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="8aff8-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) и [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="8aff8-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="8aff8-111">Следует учитывать следующие проблемы при обработке обратного вызова удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="8aff8-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="8aff8-112">Выполнение функции удаленного взаимодействия не отражается профилировщиком API, поэтому получение уведомлений для функций, которые вызываются от клиента и выполняются на сервере не выполняется должным образом.</span><span class="sxs-lookup"><span data-stu-id="8aff8-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="8aff8-113">Фактический вызов происходит через прокси-объект; Профилировщик впечатление, что некоторые функции являются JIT-компиляции, но никогда не используются.</span><span class="sxs-lookup"><span data-stu-id="8aff8-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="8aff8-114">Профилировщик не принимает точные оповещения для асинхронных событий удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="8aff8-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aff8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="8aff8-115">Requirements</span></span>  
 <span data-ttu-id="8aff8-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8aff8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aff8-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8aff8-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8aff8-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8aff8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8aff8-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aff8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aff8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8aff8-120">See Also</span></span>  
 [<span data-ttu-id="8aff8-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8aff8-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
