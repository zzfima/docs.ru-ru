---
title: "Метод ICorProfilerCallback::RemotingServerSendingReply"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerSendingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f8fa5a81231c8181e0d0257a1bbfdb4a1f0a7a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="bfa85-102">Метод ICorProfilerCallback::RemotingServerSendingReply</span><span class="sxs-lookup"><span data-stu-id="bfa85-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="bfa85-103">Уведомляет профилировщик, что процесс завершил обработку удаленного запроса вызова метода и собирается передачи ответа по каналу.</span><span class="sxs-lookup"><span data-stu-id="bfa85-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfa85-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bfa85-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bfa85-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="bfa85-106">[in] Указатель на идентификатор GUID, которое соответствует значению, указанному в [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="bfa85-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="bfa85-107">Файлы cookie для GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="bfa85-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="bfa85-108">Канал успешно передать сообщение.</span><span class="sxs-lookup"><span data-stu-id="bfa85-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="bfa85-109">Файлы cookie для GUID активны на клиентский процесс.</span><span class="sxs-lookup"><span data-stu-id="bfa85-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="bfa85-110">Это позволяет легко создавать пары вызовов удаленного взаимодействия и Создание логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="bfa85-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="bfa85-111">[in] Значение, которое является `true` Если вызов является асинхронной; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="bfa85-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfa85-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bfa85-112">Requirements</span></span>  
 <span data-ttu-id="bfa85-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfa85-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfa85-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bfa85-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bfa85-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfa85-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfa85-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfa85-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa85-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bfa85-117">See Also</span></span>  
 [<span data-ttu-id="bfa85-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bfa85-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
