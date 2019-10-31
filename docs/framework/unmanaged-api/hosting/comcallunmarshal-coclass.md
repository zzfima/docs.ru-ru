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
ms.openlocfilehash: 38f3140a181deae1a86569bfc2eb7cf3cd7d1991
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131930"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="5d439-102">Компонентный класс ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="5d439-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="5d439-103">Предоставляет интерфейсы для управления упаковкой указателей интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5d439-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d439-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d439-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="5d439-105">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="5d439-105">Interfaces</span></span>  
  
|<span data-ttu-id="5d439-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="5d439-106">Interface</span></span>|<span data-ttu-id="5d439-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5d439-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="5d439-108">Предоставляет методы для создания, инициализации и управления прокси-сервером в клиентском процессе.</span><span class="sxs-lookup"><span data-stu-id="5d439-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d439-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5d439-109">Requirements</span></span>  
 <span data-ttu-id="5d439-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d439-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d439-111">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="5d439-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="5d439-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5d439-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d439-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d439-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d439-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5d439-114">See also</span></span>

- [<span data-ttu-id="5d439-115">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="5d439-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
