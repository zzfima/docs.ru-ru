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
ms.openlocfilehash: f7a943627e2087e6b8c78ced9fc32824843d44fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175139"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="e725b-102">Метод ICorProfilerCallback::RemotingClientReceivingReply</span><span class="sxs-lookup"><span data-stu-id="e725b-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="e725b-103">Уведомляет профайлера о том, что часть вызова на стороне сервера перемотающего вызова завершена и клиент получает и собирается обработать ответ.</span><span class="sxs-lookup"><span data-stu-id="e725b-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e725b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e725b-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a><span data-ttu-id="e725b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e725b-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="e725b-106">(в) Значение, которое будет соответствовать значению, предоставленному в [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) в следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="e725b-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="e725b-107">Ремотивация GUID печенье активны.</span><span class="sxs-lookup"><span data-stu-id="e725b-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="e725b-108">Каналу удается передать сообщение.</span><span class="sxs-lookup"><span data-stu-id="e725b-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="e725b-109">GuiD-файлы cookie активны в процессе на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="e725b-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="e725b-110">Это позволяет легко спаривать перемотание вызовов.</span><span class="sxs-lookup"><span data-stu-id="e725b-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="e725b-111">(в) Значение, `true` если вызов является асинхронным; в `false`противном случае, .</span><span class="sxs-lookup"><span data-stu-id="e725b-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e725b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e725b-112">Requirements</span></span>  
 <span data-ttu-id="e725b-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e725b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e725b-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e725b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e725b-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e725b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e725b-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e725b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e725b-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e725b-117">See also</span></span>

- [<span data-ttu-id="e725b-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e725b-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
