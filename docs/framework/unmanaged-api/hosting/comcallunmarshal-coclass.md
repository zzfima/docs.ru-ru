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
ms.openlocfilehash: fde42e3ecfac81a168920bc152833be7ba72b995
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779086"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="8d485-102">Компонентный класс ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="8d485-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="8d485-103">Предоставляет интерфейсы для управления маршалингом указателей интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8d485-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d485-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d485-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="8d485-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="8d485-105">Interfaces</span></span>  
  
|<span data-ttu-id="8d485-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="8d485-106">Interface</span></span>|<span data-ttu-id="8d485-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8d485-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="8d485-108">Предоставляет методы для создания, инициализации и управления прокси в клиентский процесс.</span><span class="sxs-lookup"><span data-stu-id="8d485-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8d485-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8d485-109">Requirements</span></span>  
 <span data-ttu-id="8d485-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d485-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d485-111">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="8d485-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="8d485-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d485-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d485-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d485-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d485-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8d485-114">See also</span></span>

- [<span data-ttu-id="8d485-115">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="8d485-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
