---
title: Метод ICorProfilerCallback::RemotingServerReceivingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bc3e48185c3bc289a4f7bfd865f69d9c06a720c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750511"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="9ed8a-102">Метод ICorProfilerCallback::RemotingServerReceivingMessage</span><span class="sxs-lookup"><span data-stu-id="9ed8a-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="9ed8a-103">Уведомляет профилировщик, что процесс получил запрос или активации с помощью вызова удаленного метода.</span><span class="sxs-lookup"><span data-stu-id="9ed8a-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ed8a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ed8a-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ed8a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ed8a-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="9ed8a-106">[in] Значение, будет соответствовать со значением в [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) в этих условиях:</span><span class="sxs-lookup"><span data-stu-id="9ed8a-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="9ed8a-107">Файлы cookie для GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="9ed8a-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="9ed8a-108">Каналу удалось передать сообщение.</span><span class="sxs-lookup"><span data-stu-id="9ed8a-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="9ed8a-109">Файлы cookie GUID активны на процесс на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="9ed8a-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="9ed8a-110">Это позволяет легко создавать пары вызовов удаленного взаимодействия и Создание логического стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="9ed8a-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="9ed8a-111">[in] Значение, которое является `true` Если вызов выполняется асинхронно; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9ed8a-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ed8a-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="9ed8a-112">Remarks</span></span>  
 <span data-ttu-id="9ed8a-113">Если запрос сообщения является асинхронным, запрос может обслуживаться произвольным потоком.</span><span class="sxs-lookup"><span data-stu-id="9ed8a-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ed8a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9ed8a-114">Requirements</span></span>  
 <span data-ttu-id="9ed8a-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ed8a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ed8a-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9ed8a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9ed8a-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ed8a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ed8a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ed8a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed8a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9ed8a-119">See also</span></span>

- [<span data-ttu-id="9ed8a-120">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9ed8a-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
