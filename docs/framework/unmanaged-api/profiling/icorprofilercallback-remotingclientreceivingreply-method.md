---
title: "Метод ICorProfilerCallback::RemotingClientReceivingReply"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientReceivingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 831ce047f38f7f4a5c7a8b84efea423c482a418d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="b810e-102">Метод ICorProfilerCallback::RemotingClientReceivingReply</span><span class="sxs-lookup"><span data-stu-id="b810e-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="b810e-103">Уведомляет профилировщик, серверную часть вызова удаленного взаимодействия завершена, и теперь получает клиента и сведения для обработки ответа.</span><span class="sxs-lookup"><span data-stu-id="b810e-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b810e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b810e-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="b810e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b810e-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="b810e-106">[in] Значение, будет соответствовать со значением в [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="b810e-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="b810e-107">Файлы cookie для GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="b810e-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="b810e-108">Канал успешно передать сообщение.</span><span class="sxs-lookup"><span data-stu-id="b810e-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="b810e-109">Файлы cookie GUID активны в процессе стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="b810e-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="b810e-110">Это позволяет легко создавать пары вызовов удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="b810e-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="b810e-111">[in] Значение, которое является `true` Если вызов является асинхронной; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="b810e-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b810e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b810e-112">Requirements</span></span>  
 <span data-ttu-id="b810e-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b810e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b810e-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b810e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b810e-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b810e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b810e-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b810e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b810e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b810e-117">See Also</span></span>  
 [<span data-ttu-id="b810e-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b810e-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
