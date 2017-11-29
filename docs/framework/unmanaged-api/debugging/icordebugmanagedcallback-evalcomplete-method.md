---
title: "Метод ICorDebugManagedCallback::EvalComplete"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.EvalComplete
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6211a5f0038c6244f7732e0c0ba854aaa1e6092e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="15a7b-102">Метод ICorDebugManagedCallback::EvalComplete</span><span class="sxs-lookup"><span data-stu-id="15a7b-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="15a7b-103">Уведомляет отладчик о завершении вычисления.</span><span class="sxs-lookup"><span data-stu-id="15a7b-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15a7b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15a7b-104">Syntax</span></span>  
  
```  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15a7b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15a7b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="15a7b-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в которой была выполнена оценка.</span><span class="sxs-lookup"><span data-stu-id="15a7b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="15a7b-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в которой была выполнена оценка.</span><span class="sxs-lookup"><span data-stu-id="15a7b-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="15a7b-108">[in] Указатель на объект ICorDebugEval, который представляет код, который выполняется вычисление.</span><span class="sxs-lookup"><span data-stu-id="15a7b-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15a7b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="15a7b-109">Requirements</span></span>  
 <span data-ttu-id="15a7b-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15a7b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15a7b-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15a7b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15a7b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15a7b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15a7b-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15a7b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a7b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="15a7b-114">See Also</span></span>  
 [<span data-ttu-id="15a7b-115">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="15a7b-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
