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
ms.openlocfilehash: 07cab119810c4da25d16a4ad7c13f2d2bda16455
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140311"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="33a71-102">Перечисление METAHOST_CONFIG_FLAGS</span><span class="sxs-lookup"><span data-stu-id="33a71-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="33a71-103">Описывает возможные флаги, возвращаемые в параметре `pdwConfigFlags` метода [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , который указывает на присутствие и настройку атрибута `useLegacyV2RuntimeActivationPolicy` в [элементе\<Startup > элемента](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="33a71-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33a71-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33a71-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="33a71-105">Члены</span><span class="sxs-lookup"><span data-stu-id="33a71-105">Members</span></span>  
  
|<span data-ttu-id="33a71-106">Член</span><span class="sxs-lookup"><span data-stu-id="33a71-106">Member</span></span>|<span data-ttu-id="33a71-107">Описание</span><span class="sxs-lookup"><span data-stu-id="33a71-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="33a71-108">Атрибут `useLegacyV2RuntimeActivationPolicy` отсутствует в [элементе > запуска\<](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="33a71-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="33a71-109">Атрибут `useLegacyV2RuntimeActivationPolicy` присутствовал и имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="33a71-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="33a71-110">Атрибут `useLegacyV2RuntimeActivationPolicy` присутствовал и имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="33a71-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="33a71-111">Примените эту маску к значению, возвращенному в `pdwConfigFlags`, чтобы получить значения, относящиеся к `useLegacyV2RuntimeActivationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="33a71-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33a71-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="33a71-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33a71-113">Требования</span><span class="sxs-lookup"><span data-stu-id="33a71-113">Requirements</span></span>  
 <span data-ttu-id="33a71-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33a71-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33a71-115">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="33a71-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="33a71-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="33a71-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33a71-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33a71-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a71-118">См. также</span><span class="sxs-lookup"><span data-stu-id="33a71-118">See also</span></span>

- [<span data-ttu-id="33a71-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="33a71-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="33a71-120">Метод GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="33a71-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="33a71-121">Элемент \<startup></span><span class="sxs-lookup"><span data-stu-id="33a71-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
