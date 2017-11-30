---
title: "Метод ICorThreadpool::CorCreateTimer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorThreadpool.CorCreateTimer
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 70a7c389ac44e8a513ec8a764d19c9a316ca7c08
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="f2f85-102">Метод ICorThreadpool::CorCreateTimer</span><span class="sxs-lookup"><span data-stu-id="f2f85-102">ICorThreadpool::CorCreateTimer Method</span></span>
<span data-ttu-id="f2f85-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="f2f85-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2f85-104">Syntax</span></span>  
  
```  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f2f85-105">Требования</span><span class="sxs-lookup"><span data-stu-id="f2f85-105">Requirements</span></span>  
 <span data-ttu-id="f2f85-106">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2f85-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2f85-107">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2f85-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2f85-108">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2f85-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2f85-109">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2f85-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f85-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f2f85-110">See Also</span></span>  
 [<span data-ttu-id="f2f85-111">Icorthreadpool-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f2f85-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
