---
title: Компонентный класс ComCallUnmarshal
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
ms.openlocfilehash: 2f17a88a90905006432ae8c5dc040277124c947b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166885"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="a1186-102">Компонентный класс ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="a1186-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="a1186-103">Предоставляет интерфейсы для управления маршалингом указателей интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a1186-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1186-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1186-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="a1186-105">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="a1186-105">Interfaces</span></span>  
  
|<span data-ttu-id="a1186-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="a1186-106">Interface</span></span>|<span data-ttu-id="a1186-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a1186-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="a1186-108">Предоставляет методы для создания, инициализации и управления прокси в клиентский процесс.</span><span class="sxs-lookup"><span data-stu-id="a1186-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1186-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a1186-109">Requirements</span></span>  
 <span data-ttu-id="a1186-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1186-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1186-111">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="a1186-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="a1186-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1186-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a1186-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a1186-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a1186-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a1186-114">See also</span></span>

- [<span data-ttu-id="a1186-115">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="a1186-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
