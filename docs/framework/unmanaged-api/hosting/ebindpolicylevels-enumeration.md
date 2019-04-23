---
title: Перечисление EBindPolicyLevels
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8f2b08662e719a3308a62ab5b60f5dc490f2a6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142211"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="28ae0-102">Перечисление EBindPolicyLevels</span><span class="sxs-lookup"><span data-stu-id="28ae0-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="28ae0-103">Предоставляет флаги для указания уровня, по которому следует применить или изменить политику сборок.</span><span class="sxs-lookup"><span data-stu-id="28ae0-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ae0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28ae0-104">Syntax</span></span>  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="28ae0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="28ae0-105">Members</span></span>  
  
|<span data-ttu-id="28ae0-106">Член</span><span class="sxs-lookup"><span data-stu-id="28ae0-106">Member</span></span>|<span data-ttu-id="28ae0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="28ae0-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="28ae0-108">Указывает, что политика должна применяться на уровне администратора.</span><span class="sxs-lookup"><span data-stu-id="28ae0-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="28ae0-109">Указывает, что политика должна применяться на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="28ae0-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="28ae0-110">Указывает, что политика должна применяться на уровне узла.</span><span class="sxs-lookup"><span data-stu-id="28ae0-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="28ae0-111">Указывает флаги не уровня политики.</span><span class="sxs-lookup"><span data-stu-id="28ae0-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="28ae0-112">Указывает, что политика должна применяться на уровне издателя.</span><span class="sxs-lookup"><span data-stu-id="28ae0-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="28ae0-113">Указывает, что политика применяется на уровнях переменной.</span><span class="sxs-lookup"><span data-stu-id="28ae0-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="28ae0-114">Указывает, что политики должно поддерживать переносимости между реализациями сборки платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="28ae0-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="28ae0-115">См. в разделе [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) элемент файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="28ae0-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="28ae0-116">Указывает, что политика должна соответствовать политике, общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="28ae0-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28ae0-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="28ae0-117">Remarks</span></span>  
 <span data-ttu-id="28ae0-118">Это перечисление передается методам [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) интерфейс для выполнения изменений в политике приложения.</span><span class="sxs-lookup"><span data-stu-id="28ae0-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28ae0-119">Требования</span><span class="sxs-lookup"><span data-stu-id="28ae0-119">Requirements</span></span>  
 <span data-ttu-id="28ae0-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28ae0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28ae0-121">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="28ae0-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28ae0-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28ae0-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28ae0-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28ae0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ae0-124">См. также</span><span class="sxs-lookup"><span data-stu-id="28ae0-124">See also</span></span>

- [<span data-ttu-id="28ae0-125">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="28ae0-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="28ae0-126">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="28ae0-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
