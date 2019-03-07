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
ms.openlocfilehash: fff5b25706353d999ab6875092e31f554438f28c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469161"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="155fd-102">Метод ICorProfilerCallback::RemotingClientReceivingReply</span><span class="sxs-lookup"><span data-stu-id="155fd-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="155fd-103">Уведомляет профилировщик, что серверная часть вызова удаленного взаимодействия завершена, клиент принимает ответ и готов к его обработке.</span><span class="sxs-lookup"><span data-stu-id="155fd-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="155fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="155fd-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
## <a name="parameters"></a><span data-ttu-id="155fd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="155fd-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="155fd-106">[in] Значение, будет соответствовать со значением в [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) в этих условиях:</span><span class="sxs-lookup"><span data-stu-id="155fd-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="155fd-107">Файлы cookie для GUID удаленного взаимодействия активны.</span><span class="sxs-lookup"><span data-stu-id="155fd-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="155fd-108">Каналу удалось передать сообщение.</span><span class="sxs-lookup"><span data-stu-id="155fd-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="155fd-109">Файлы cookie GUID активны на процесс на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="155fd-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="155fd-110">Это позволяет легко создавать пары вызовов удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="155fd-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="155fd-111">[in] Значение, которое является `true` Если вызов выполняется асинхронно; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="155fd-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="155fd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="155fd-112">Requirements</span></span>  
 <span data-ttu-id="155fd-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="155fd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="155fd-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="155fd-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="155fd-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="155fd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="155fd-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="155fd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="155fd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="155fd-117">See also</span></span>
- [<span data-ttu-id="155fd-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="155fd-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
