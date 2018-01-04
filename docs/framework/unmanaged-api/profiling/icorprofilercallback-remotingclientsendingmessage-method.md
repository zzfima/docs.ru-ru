---
title: "Метод ICorProfilerCallback::RemotingClientSendingMessage"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientSendingMessage
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d22843c3489aae24003df1e91b0cae4481f4599c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="13621-102">Метод ICorProfilerCallback::RemotingClientSendingMessage</span><span class="sxs-lookup"><span data-stu-id="13621-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="13621-103">Уведомляет профилировщик о том, что клиент отправляет запрос на сервер.</span><span class="sxs-lookup"><span data-stu-id="13621-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13621-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13621-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13621-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="13621-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="13621-106">[in] Значение, соответствующее значение в [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="13621-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="13621-107">Файлы cookie для GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="13621-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="13621-108">Канал успешно передать сообщение.</span><span class="sxs-lookup"><span data-stu-id="13621-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="13621-109">Файлы cookie GUID активны в процессе стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="13621-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="13621-110">Это позволяет легко создавать пары вызовов удаленного взаимодействия и Создание логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="13621-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="13621-111">[in] Значение, которое является `true` Если вызов является асинхронной; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="13621-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13621-112">Требования</span><span class="sxs-lookup"><span data-stu-id="13621-112">Requirements</span></span>  
 <span data-ttu-id="13621-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13621-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13621-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="13621-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="13621-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13621-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13621-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13621-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13621-117">См. также</span><span class="sxs-lookup"><span data-stu-id="13621-117">See Also</span></span>  
 [<span data-ttu-id="13621-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="13621-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
