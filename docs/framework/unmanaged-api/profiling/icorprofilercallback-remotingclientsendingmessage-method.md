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
ms.openlocfilehash: 424e0323c018367560d4cf3542e9e8668575a03f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675247"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="2ec51-102">Метод ICorProfilerCallback::RemotingClientSendingMessage</span><span class="sxs-lookup"><span data-stu-id="2ec51-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="2ec51-103">Уведомляет профилировщик о том, что клиент отправляет запрос к серверу.</span><span class="sxs-lookup"><span data-stu-id="2ec51-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ec51-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ec51-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ec51-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ec51-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="2ec51-106">[in] Значение, которое соответствует со значением в [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) в этих условиях:</span><span class="sxs-lookup"><span data-stu-id="2ec51-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="2ec51-107">Файлы cookie для GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="2ec51-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="2ec51-108">Каналу удалось передать сообщение.</span><span class="sxs-lookup"><span data-stu-id="2ec51-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="2ec51-109">Файлы cookie GUID активны на процесс на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="2ec51-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="2ec51-110">Это позволяет легко создавать пары вызовов удаленного взаимодействия и Создание логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="2ec51-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="2ec51-111">[in] Значение, которое является `true` Если вызов выполняется асинхронно; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2ec51-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ec51-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2ec51-112">Requirements</span></span>  
 <span data-ttu-id="2ec51-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ec51-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ec51-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2ec51-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2ec51-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ec51-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ec51-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ec51-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec51-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2ec51-117">See also</span></span>
- [<span data-ttu-id="2ec51-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2ec51-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
