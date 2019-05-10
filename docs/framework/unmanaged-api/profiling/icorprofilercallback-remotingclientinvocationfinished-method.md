---
title: Метод ICorProfilerCallback::RemotingClientInvocationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c3f7c30518184be70c85ff096915738b1633a01
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64603235"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="65577-102">Метод ICorProfilerCallback::RemotingClientInvocationFinished</span><span class="sxs-lookup"><span data-stu-id="65577-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="65577-103">Уведомляет профилировщик о запуске удаленного вызова для завершения на клиенте.</span><span class="sxs-lookup"><span data-stu-id="65577-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65577-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65577-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="65577-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="65577-105">Remarks</span></span>  
 <span data-ttu-id="65577-106">Если синхронный вызов удаленного взаимодействия, она также выполняться до завершения на сервере.</span><span class="sxs-lookup"><span data-stu-id="65577-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="65577-107">В случае асинхронного вызова удаленного взаимодействия ответ по-прежнему можно ожидать при обработке вызова.</span><span class="sxs-lookup"><span data-stu-id="65577-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="65577-108">Если ожидается ответ, он будет выполняться как вызов [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) и дополнительный вызов `RemotingClientInvocationFinished` для указания необходимых дополнительной обработки асинхронного вызова.</span><span class="sxs-lookup"><span data-stu-id="65577-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="65577-109">Каждая из следующих пар обратных вызовов произойдет на том же потоке.</span><span class="sxs-lookup"><span data-stu-id="65577-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="65577-110">`RemotingClientInvocationStarted` и [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="65577-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="65577-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) и [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="65577-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="65577-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) и [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="65577-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="65577-113">Следует иметь в виду следующие проблемы с обратные вызовы удаленного взаимодействия:</span><span class="sxs-lookup"><span data-stu-id="65577-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="65577-114">Выполнение функции удаленного взаимодействия не отражается профилировщиком API, поэтому получение уведомлений для функций, которые вызываются из клиента и выполняются на сервере не выполняется должным образом.</span><span class="sxs-lookup"><span data-stu-id="65577-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="65577-115">Фактический вызов происходит через объект прокси-сервера; для профилировщика похоже, что определенные функции являются JIT-компиляции, но никогда не используются.</span><span class="sxs-lookup"><span data-stu-id="65577-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="65577-116">Профилировщик не получать точные уведомления о событиях асинхронное удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="65577-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65577-117">Требования</span><span class="sxs-lookup"><span data-stu-id="65577-117">Requirements</span></span>  
 <span data-ttu-id="65577-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65577-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65577-119">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="65577-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="65577-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65577-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65577-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65577-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65577-122">См. также</span><span class="sxs-lookup"><span data-stu-id="65577-122">See also</span></span>

- [<span data-ttu-id="65577-123">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="65577-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
