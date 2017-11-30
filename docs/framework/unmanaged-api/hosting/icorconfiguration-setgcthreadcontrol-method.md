---
title: "Метод ICorConfiguration::SetGCThreadControl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetGCThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1dfcff8a12f808c75a9e69486f802f8b886c468b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="c8b72-102">Метод ICorConfiguration::SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="c8b72-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="c8b72-103">Задает интерфейс обратного вызова для планирования потоков без выполнения задач, которые в противном случае были бы заблокированы для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c8b72-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8b72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8b72-104">Syntax</span></span>  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8b72-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c8b72-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="c8b72-106">[in] Указатель на [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) объект, который уведомляет основное приложение о приостановки потоков для задач, отличных от среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c8b72-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8b72-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c8b72-107">Remarks</span></span>  
 <span data-ttu-id="c8b72-108">Выбрать узел в [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) обратного вызова необходимость повторного планирования в потоке.</span><span class="sxs-lookup"><span data-stu-id="c8b72-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8b72-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c8b72-109">Requirements</span></span>  
 <span data-ttu-id="c8b72-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8b72-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8b72-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8b72-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8b72-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8b72-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8b72-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8b72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b72-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c8b72-114">See Also</span></span>  
 [<span data-ttu-id="c8b72-115">Icorconfiguration-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c8b72-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
