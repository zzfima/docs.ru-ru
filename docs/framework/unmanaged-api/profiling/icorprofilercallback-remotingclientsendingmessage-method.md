---
title: Метод ICorProfilerCallback::RemotingClientSendingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14717b67db03b941d33b5df61c64b5df078adaa2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="41551-102">Метод ICorProfilerCallback::RemotingClientSendingMessage</span><span class="sxs-lookup"><span data-stu-id="41551-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="41551-103">Уведомляет профилировщик о том, что клиент отправляет запрос на сервер.</span><span class="sxs-lookup"><span data-stu-id="41551-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41551-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41551-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41551-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="41551-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="41551-106">[in] Значение, соответствующее значение в [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="41551-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="41551-107">Файлы cookie для GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="41551-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="41551-108">Канал успешно передать сообщение.</span><span class="sxs-lookup"><span data-stu-id="41551-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="41551-109">Файлы cookie GUID активны в процессе стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="41551-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="41551-110">Это позволяет легко создавать пары вызовов удаленного взаимодействия и Создание логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="41551-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="41551-111">[in] Значение, которое является `true` Если вызов является асинхронной; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="41551-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41551-112">Требования</span><span class="sxs-lookup"><span data-stu-id="41551-112">Requirements</span></span>  
 <span data-ttu-id="41551-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41551-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41551-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41551-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41551-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41551-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41551-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41551-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41551-117">См. также</span><span class="sxs-lookup"><span data-stu-id="41551-117">See Also</span></span>  
 [<span data-ttu-id="41551-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="41551-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
