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
ms.openlocfilehash: 36792d01ebdad72271a8b0597a33d83cab34780e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59114034"
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="1488e-102">Перечисление CLSID_RESOLUTION_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1488e-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="1488e-103">Содержит значения, указывающие способ разрешения общеязыковой среды выполнения (CLR) `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="1488e-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1488e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1488e-104">Syntax</span></span>  
  
```  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="1488e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="1488e-105">Members</span></span>  
  
|<span data-ttu-id="1488e-106">Член</span><span class="sxs-lookup"><span data-stu-id="1488e-106">Member</span></span>|<span data-ttu-id="1488e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1488e-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="1488e-108">Задает поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1488e-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="1488e-109">Указывает, что среда выполнения ищет в реестре и применяет политику оболочки.</span><span class="sxs-lookup"><span data-stu-id="1488e-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1488e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1488e-110">Requirements</span></span>  
 <span data-ttu-id="1488e-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1488e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1488e-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1488e-112">**Header:** MSCorEE.h</span></span>  
  
 **<span data-ttu-id="1488e-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1488e-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1488e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1488e-114">See also</span></span>

- [<span data-ttu-id="1488e-115">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="1488e-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
