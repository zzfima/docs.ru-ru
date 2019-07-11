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
ms.openlocfilehash: 4729a8d3ac2c6f7ec51a032a07ebfd1c2838cb9a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782906"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="15a5a-102">Метод ICorProfilerCallback::RemotingClientSendingMessage</span><span class="sxs-lookup"><span data-stu-id="15a5a-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="15a5a-103">Уведомляет профилировщик о том, что клиент отправляет запрос к серверу.</span><span class="sxs-lookup"><span data-stu-id="15a5a-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15a5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15a5a-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15a5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15a5a-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="15a5a-106">[in] Значение, которое соответствует со значением в [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) в этих условиях:</span><span class="sxs-lookup"><span data-stu-id="15a5a-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="15a5a-107">Файлы cookie для GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="15a5a-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="15a5a-108">Каналу удалось передать сообщение.</span><span class="sxs-lookup"><span data-stu-id="15a5a-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="15a5a-109">Файлы cookie GUID активны на процесс на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="15a5a-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="15a5a-110">Это позволяет легко создавать пары вызовов удаленного взаимодействия и Создание логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="15a5a-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="15a5a-111">[in] Значение, которое является `true` Если вызов выполняется асинхронно; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="15a5a-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15a5a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="15a5a-112">Requirements</span></span>  
 <span data-ttu-id="15a5a-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15a5a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15a5a-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15a5a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="15a5a-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15a5a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15a5a-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15a5a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a5a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="15a5a-117">See also</span></span>

- [<span data-ttu-id="15a5a-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="15a5a-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
