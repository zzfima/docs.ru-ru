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
ms.openlocfilehash: 81aef6beb9ee6d622519738d24fdd0a4d42a75b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136555"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="98ec4-102">Перечисление EBindPolicyLevels</span><span class="sxs-lookup"><span data-stu-id="98ec4-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="98ec4-103">Предоставляет флаги для указания уровня применения или изменения политики сборки.</span><span class="sxs-lookup"><span data-stu-id="98ec4-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98ec4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98ec4-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="98ec4-105">Члены</span><span class="sxs-lookup"><span data-stu-id="98ec4-105">Members</span></span>  
  
|<span data-ttu-id="98ec4-106">Член</span><span class="sxs-lookup"><span data-stu-id="98ec4-106">Member</span></span>|<span data-ttu-id="98ec4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="98ec4-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="98ec4-108">Указывает, что политику следует применять на уровне администратора.</span><span class="sxs-lookup"><span data-stu-id="98ec4-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="98ec4-109">Указывает, что политику следует применять на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="98ec4-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="98ec4-110">Указывает, что политику следует применять на уровне узла.</span><span class="sxs-lookup"><span data-stu-id="98ec4-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="98ec4-111">Указывает отсутствие флагов уровня политики.</span><span class="sxs-lookup"><span data-stu-id="98ec4-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="98ec4-112">Указывает, что политика должна применяться на уровне издателя.</span><span class="sxs-lookup"><span data-stu-id="98ec4-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="98ec4-113">Указывает, что политика должна быть применима на уровнях переменных.</span><span class="sxs-lookup"><span data-stu-id="98ec4-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="98ec4-114">Указывает, что политика должна поддерживать переносимость между реализациями сборки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="98ec4-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="98ec4-115">См. раздел файла конфигурации [\<тег supportportability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) .</span><span class="sxs-lookup"><span data-stu-id="98ec4-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="98ec4-116">Указывает, что политика должна быть унифицированной для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="98ec4-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98ec4-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="98ec4-117">Remarks</span></span>  
 <span data-ttu-id="98ec4-118">Это перечисление передается методам интерфейса [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) для указания изменений в политике приложения.</span><span class="sxs-lookup"><span data-stu-id="98ec4-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98ec4-119">Требования</span><span class="sxs-lookup"><span data-stu-id="98ec4-119">Requirements</span></span>  
 <span data-ttu-id="98ec4-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98ec4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98ec4-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="98ec4-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98ec4-122">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="98ec4-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98ec4-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98ec4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ec4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="98ec4-124">See also</span></span>

- [<span data-ttu-id="98ec4-125">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="98ec4-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="98ec4-126">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="98ec4-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
