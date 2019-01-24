---
title: Перечисление CLSID_RESOLUTION_FLAGS
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bee25122920a6fcec3bbd4e9e53bbdad008d5304
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514117"
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="39518-102">Перечисление CLSID_RESOLUTION_FLAGS</span><span class="sxs-lookup"><span data-stu-id="39518-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="39518-103">Содержит значения, указывающие способ разрешения общеязыковой среды выполнения (CLR) `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="39518-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39518-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39518-104">Syntax</span></span>  
  
```  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="39518-105">Участники</span><span class="sxs-lookup"><span data-stu-id="39518-105">Members</span></span>  
  
|<span data-ttu-id="39518-106">Член</span><span class="sxs-lookup"><span data-stu-id="39518-106">Member</span></span>|<span data-ttu-id="39518-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="39518-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="39518-108">Задает поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="39518-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="39518-109">Указывает, что среда выполнения ищет в реестре и применяет политику оболочки.</span><span class="sxs-lookup"><span data-stu-id="39518-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="39518-110">Требования</span><span class="sxs-lookup"><span data-stu-id="39518-110">Requirements</span></span>  
 <span data-ttu-id="39518-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39518-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39518-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="39518-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39518-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39518-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39518-114">См. также</span><span class="sxs-lookup"><span data-stu-id="39518-114">See also</span></span>
- [<span data-ttu-id="39518-115">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="39518-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
