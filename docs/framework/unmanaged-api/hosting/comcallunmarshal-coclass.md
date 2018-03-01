---
title: "Кокласс ComCallUnmarshal"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2cbaefd2b2c3b79a97107f4aaa394a3db2c68b33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="b75bb-102">Кокласс ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="b75bb-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="b75bb-103">Предоставляет интерфейсы для управления маршалингом указателей интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b75bb-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b75bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b75bb-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="b75bb-105">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="b75bb-105">Interfaces</span></span>  
  
|<span data-ttu-id="b75bb-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="b75bb-106">Interface</span></span>|<span data-ttu-id="b75bb-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b75bb-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="b75bb-108">Предоставляет методы для создания, инициализации и управления прокси в клиентском процессе.</span><span class="sxs-lookup"><span data-stu-id="b75bb-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b75bb-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b75bb-109">Requirements</span></span>  
 <span data-ttu-id="b75bb-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b75bb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b75bb-111">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="b75bb-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b75bb-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b75bb-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b75bb-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b75bb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b75bb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b75bb-114">See Also</span></span>  
 [<span data-ttu-id="b75bb-115">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="b75bb-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
