---
title: Метод ICorProfilerCallback::RemotingServerSendingReply
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
ms.openlocfilehash: f77901623ef4df7b43276c18a910cf62fcc4451d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865978"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="8ffbc-102">Метод ICorProfilerCallback::RemotingServerSendingReply</span><span class="sxs-lookup"><span data-stu-id="8ffbc-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="8ffbc-103">Уведомляет профилировщик о том, что процесс завершил обработку запроса удаленного вызова метода и собирается передать ответ через канал.</span><span class="sxs-lookup"><span data-stu-id="8ffbc-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ffbc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ffbc-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ffbc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ffbc-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="8ffbc-106">окне Указатель на идентификатор GUID, который будет соответствовать значению, указанному в параметре [ICorProfilerCallback:: ремотингклиентрецеивингрепли](icorprofilercallback-remotingclientreceivingreply-method.md) в следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="8ffbc-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="8ffbc-107">Файлы Cookie GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="8ffbc-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="8ffbc-108">Канал проходит успешную передачу сообщения.</span><span class="sxs-lookup"><span data-stu-id="8ffbc-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="8ffbc-109">Файлы Cookie GUID активны в процессе на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="8ffbc-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="8ffbc-110">Это позволяет легко связывать вызовы удаленного взаимодействия и создавать логические стеки вызовов.</span><span class="sxs-lookup"><span data-stu-id="8ffbc-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="8ffbc-111">окне Значение, которое `true`, если вызов является асинхронным; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="8ffbc-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ffbc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8ffbc-112">Requirements</span></span>  
 <span data-ttu-id="8ffbc-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ffbc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ffbc-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8ffbc-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8ffbc-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ffbc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ffbc-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ffbc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ffbc-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ffbc-117">See also</span></span>

- [<span data-ttu-id="8ffbc-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8ffbc-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
