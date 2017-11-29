---
title: "Метод ICorProfilerCallback::RemotingServerReceivingMessage"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerReceivingMessage
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5947541204edf7fd4359dfa3aca78ea62c8009c6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="27aa3-102">Метод ICorProfilerCallback::RemotingServerReceivingMessage</span><span class="sxs-lookup"><span data-stu-id="27aa3-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="27aa3-103">Уведомляет профилировщик, что процесс получил запрос удаленного метода вызова или активации.</span><span class="sxs-lookup"><span data-stu-id="27aa3-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27aa3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27aa3-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27aa3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27aa3-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="27aa3-106">[in] Значение, будет соответствовать со значением в [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="27aa3-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="27aa3-107">Файлы cookie для GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="27aa3-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="27aa3-108">Канал успешно передать сообщение.</span><span class="sxs-lookup"><span data-stu-id="27aa3-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="27aa3-109">Файлы cookie для GUID активны на клиентский процесс.</span><span class="sxs-lookup"><span data-stu-id="27aa3-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="27aa3-110">Это позволяет легко создавать пары вызовов удаленного взаимодействия и Создание логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="27aa3-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="27aa3-111">[in] Значение, которое является `true` Если вызов является асинхронной; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="27aa3-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27aa3-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="27aa3-112">Remarks</span></span>  
 <span data-ttu-id="27aa3-113">Если запрос сообщения является асинхронным, запрос может обслуживаться произвольным потоком.</span><span class="sxs-lookup"><span data-stu-id="27aa3-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27aa3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="27aa3-114">Requirements</span></span>  
 <span data-ttu-id="27aa3-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27aa3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27aa3-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27aa3-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27aa3-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27aa3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27aa3-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27aa3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27aa3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="27aa3-119">See Also</span></span>  
 [<span data-ttu-id="27aa3-120">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="27aa3-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
