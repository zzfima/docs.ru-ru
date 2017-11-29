---
title: "Перечисление METAHOST_CONFIG_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: METAHOST_CONFIG_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: METAHOST_CONFIG_FLAGS
helpviewer_keywords: METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35b909f7b73657c8862c2d0645e5c5766df8beb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="b4aa8-102">Перечисление METAHOST_CONFIG_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b4aa8-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="b4aa8-103">Описывает возможные флаги, возвращаемых в `pdwConfigFlags` параметр [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) метод, что указывает на наличие и задание `useLegacyV2RuntimeActivationPolicy` атрибута в [ \<запуска > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b4aa8-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4aa8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4aa8-104">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b4aa8-105">Члены</span><span class="sxs-lookup"><span data-stu-id="b4aa8-105">Members</span></span>  
  
|<span data-ttu-id="b4aa8-106">Член</span><span class="sxs-lookup"><span data-stu-id="b4aa8-106">Member</span></span>|<span data-ttu-id="b4aa8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b4aa8-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="b4aa8-108">`useLegacyV2RuntimeActivationPolicy` Атрибут не найден в [ \<запуска > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="b4aa8-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="b4aa8-109">`useLegacyV2RuntimeActivationPolicy` Атрибут был представить и задать для `true`.</span><span class="sxs-lookup"><span data-stu-id="b4aa8-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="b4aa8-110">`useLegacyV2RuntimeActivationPolicy` Атрибут был представить и задать для `false`.</span><span class="sxs-lookup"><span data-stu-id="b4aa8-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="b4aa8-111">Применение этой маски равным значению, возвращенному в `pdwConfigFlags` Чтобы получить значения, относящиеся к `useLegacyV2RuntimeActivationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="b4aa8-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4aa8-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4aa8-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4aa8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b4aa8-113">Requirements</span></span>  
 <span data-ttu-id="b4aa8-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4aa8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4aa8-115">**Заголовок:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="b4aa8-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="b4aa8-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4aa8-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4aa8-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4aa8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4aa8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b4aa8-118">See Also</span></span>  
 [<span data-ttu-id="b4aa8-119">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="b4aa8-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="b4aa8-120">GetRequestedRuntime-метод</span><span class="sxs-lookup"><span data-stu-id="b4aa8-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)  
 [<span data-ttu-id="b4aa8-121">\<При запуске > элемент</span><span class="sxs-lookup"><span data-stu-id="b4aa8-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
