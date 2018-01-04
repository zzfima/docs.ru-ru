---
title: "Перечисление CLSID_RESOLUTION_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLSID_RESOLUTION_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: CLSID_RESOLUTION_FLAGS
helpviewer_keywords: CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 840e3c3c155a383f94051940b6d63dea3412bf63
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="cbcae-102">Перечисление CLSID_RESOLUTION_FLAGS</span><span class="sxs-lookup"><span data-stu-id="cbcae-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="cbcae-103">Содержит значения, указывающие способ разрешения общеязыковой среды выполнения (CLR) `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="cbcae-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbcae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbcae-104">Syntax</span></span>  
  
```  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="cbcae-105">Участники</span><span class="sxs-lookup"><span data-stu-id="cbcae-105">Members</span></span>  
  
|<span data-ttu-id="cbcae-106">Член</span><span class="sxs-lookup"><span data-stu-id="cbcae-106">Member</span></span>|<span data-ttu-id="cbcae-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="cbcae-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="cbcae-108">Задает поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cbcae-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="cbcae-109">Указывает, что среда выполнения ищет в реестре и применяет политику оболочки.</span><span class="sxs-lookup"><span data-stu-id="cbcae-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cbcae-110">Требования</span><span class="sxs-lookup"><span data-stu-id="cbcae-110">Requirements</span></span>  
 <span data-ttu-id="cbcae-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbcae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbcae-112">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cbcae-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cbcae-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbcae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbcae-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cbcae-114">See Also</span></span>  
 [<span data-ttu-id="cbcae-115">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="cbcae-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
