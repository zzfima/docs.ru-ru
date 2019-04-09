---
title: Перечисление METAHOST_CONFIG_FLAGS
ms.date: 03/30/2017
api_name:
- METAHOST_CONFIG_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_CONFIG_FLAGS
helpviewer_keywords:
- METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e322f5c7119d13c8a872bd87d00c1e55324b581
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135782"
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="78a1f-102">Перечисление METAHOST_CONFIG_FLAGS</span><span class="sxs-lookup"><span data-stu-id="78a1f-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="78a1f-103">Описывает возможные флаги, возвращаемые в `pdwConfigFlags` параметр [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) метод, что указывает на наличие и задание `useLegacyV2RuntimeActivationPolicy` атрибут в [ \<startup > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="78a1f-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a1f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78a1f-104">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="78a1f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="78a1f-105">Members</span></span>  
  
|<span data-ttu-id="78a1f-106">Член</span><span class="sxs-lookup"><span data-stu-id="78a1f-106">Member</span></span>|<span data-ttu-id="78a1f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="78a1f-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="78a1f-108">`useLegacyV2RuntimeActivationPolicy` Атрибут не присутствует в [ \<startup > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="78a1f-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="78a1f-109">`useLegacyV2RuntimeActivationPolicy` Атрибут был присутствует и имеет значение для `true`.</span><span class="sxs-lookup"><span data-stu-id="78a1f-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="78a1f-110">`useLegacyV2RuntimeActivationPolicy` Атрибут был присутствует и имеет значение для `false`.</span><span class="sxs-lookup"><span data-stu-id="78a1f-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="78a1f-111">Применение этой маски к значению, возвращенному в `pdwConfigFlags` Чтобы получить значения, относящиеся к `useLegacyV2RuntimeActivationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="78a1f-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78a1f-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="78a1f-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78a1f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="78a1f-113">Requirements</span></span>  
 <span data-ttu-id="78a1f-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78a1f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78a1f-115">**Заголовок.** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="78a1f-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="78a1f-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="78a1f-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="78a1f-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="78a1f-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="78a1f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="78a1f-118">See also</span></span>

- [<span data-ttu-id="78a1f-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="78a1f-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="78a1f-120">Метод GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="78a1f-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="78a1f-121">\<Startup > элемент</span><span class="sxs-lookup"><span data-stu-id="78a1f-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
