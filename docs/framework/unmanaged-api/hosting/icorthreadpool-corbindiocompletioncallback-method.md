---
title: "Метод ICorThreadpool::CorBindIoCompletionCallback"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorThreadpool.CorBindIoCompletionCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: CorBindIoCompletionCallback
helpviewer_keywords:
- CorBindIoCompletionCallback method [.NET Framework hosting]
- ICorThreadpool::CorBindIoCompletionCallback method [.NET Framework hosting]
ms.assetid: 2b159225-f09c-42f1-aa7c-44087e121249
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 28baf49fd659564f1e1e356f52be6cd9cbb9f643
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="46192-102">Метод ICorThreadpool::CorBindIoCompletionCallback</span><span class="sxs-lookup"><span data-stu-id="46192-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="46192-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="46192-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46192-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46192-104">Syntax</span></span>  
  
```  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="46192-105">Требования</span><span class="sxs-lookup"><span data-stu-id="46192-105">Requirements</span></span>  
 <span data-ttu-id="46192-106">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46192-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46192-107">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="46192-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46192-108">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46192-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46192-109">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46192-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46192-110">См. также</span><span class="sxs-lookup"><span data-stu-id="46192-110">See Also</span></span>  
 [<span data-ttu-id="46192-111">Icorthreadpool-интерфейс</span><span class="sxs-lookup"><span data-stu-id="46192-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
