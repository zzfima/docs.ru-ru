---
title: "Метод ICorProfilerCallback::RemotingServerInvocationReturned"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerInvocationReturned
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerInvocationReturned
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned method [.NET Framework profiling]
- RemotingServerInvocationReturned method [.NET Framework profiling]
ms.assetid: a4de6805-e159-4280-99e5-3390c86166d0
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4b1becc695b001402482256ef6adad3b339495e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="136bf-102">Метод ICorProfilerCallback::RemotingServerInvocationReturned</span><span class="sxs-lookup"><span data-stu-id="136bf-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="136bf-103">Уведомляет профилировщик, что процесс завершил вызов метода в ответ на запрос вызова удаленного метода.</span><span class="sxs-lookup"><span data-stu-id="136bf-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="136bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="136bf-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="136bf-105">Требования</span><span class="sxs-lookup"><span data-stu-id="136bf-105">Requirements</span></span>  
 <span data-ttu-id="136bf-106">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="136bf-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="136bf-107">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="136bf-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="136bf-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="136bf-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="136bf-109">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="136bf-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="136bf-110">См. также</span><span class="sxs-lookup"><span data-stu-id="136bf-110">See Also</span></span>  
 [<span data-ttu-id="136bf-111">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="136bf-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
