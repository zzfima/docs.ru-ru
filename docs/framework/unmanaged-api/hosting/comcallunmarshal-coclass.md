---
title: Кокласс ComCallUnmarshal
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a404448c45a37d50794ceae9a9bf8ff6af08eeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574577"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="3605a-102">Кокласс ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="3605a-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="3605a-103">Предоставляет интерфейсы для управления маршалингом указателей интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3605a-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3605a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3605a-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="3605a-105">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="3605a-105">Interfaces</span></span>  
  
|<span data-ttu-id="3605a-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="3605a-106">Interface</span></span>|<span data-ttu-id="3605a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3605a-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="3605a-108">Предоставляет методы для создания, инициализации и управления прокси в клиентский процесс.</span><span class="sxs-lookup"><span data-stu-id="3605a-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3605a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3605a-109">Requirements</span></span>  
 <span data-ttu-id="3605a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3605a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3605a-111">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="3605a-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="3605a-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3605a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3605a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3605a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3605a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3605a-114">See also</span></span>
- [<span data-ttu-id="3605a-115">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="3605a-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
