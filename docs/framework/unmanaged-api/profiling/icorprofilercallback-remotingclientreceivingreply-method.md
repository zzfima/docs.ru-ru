---
title: Метод ICorProfilerCallback::RemotingClientReceivingReply
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientReceivingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04956fb5519c66141f4bd7330367f6c78b4e7bc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="9fb94-102">Метод ICorProfilerCallback::RemotingClientReceivingReply</span><span class="sxs-lookup"><span data-stu-id="9fb94-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="9fb94-103">Уведомляет профилировщик, серверную часть вызова удаленного взаимодействия завершена, и теперь получает клиента и сведения для обработки ответа.</span><span class="sxs-lookup"><span data-stu-id="9fb94-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fb94-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fb94-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fb94-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9fb94-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="9fb94-106">[in] Значение, будет соответствовать со значением в [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="9fb94-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="9fb94-107">Файлы cookie для GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="9fb94-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="9fb94-108">Канал успешно передать сообщение.</span><span class="sxs-lookup"><span data-stu-id="9fb94-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="9fb94-109">Файлы cookie GUID активны в процессе стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="9fb94-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="9fb94-110">Это позволяет легко создавать пары вызовов удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9fb94-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="9fb94-111">[in] Значение, которое является `true` Если вызов является асинхронной; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="9fb94-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fb94-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9fb94-112">Requirements</span></span>  
 <span data-ttu-id="9fb94-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fb94-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fb94-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9fb94-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9fb94-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fb94-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fb94-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fb94-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fb94-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9fb94-117">See Also</span></span>  
 [<span data-ttu-id="9fb94-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9fb94-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
