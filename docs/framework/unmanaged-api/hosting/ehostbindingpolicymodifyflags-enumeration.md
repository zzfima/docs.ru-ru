---
title: "Перечисление EHostBindingPolicyModifyFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eb985cf2f34719b3aed9397155bd9d538b57dc3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="a9833-102">Перечисление EHostBindingPolicyModifyFlags</span><span class="sxs-lookup"><span data-stu-id="a9833-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="a9833-103">Позволяет узлу указать тип перенаправления, которую должен выполнить общеязыковой среды выполнения (CLR), при применении изменений политики из исходной сборки на целевую сборку.</span><span class="sxs-lookup"><span data-stu-id="a9833-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9833-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9833-104">Syntax</span></span>  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a9833-105">Участники</span><span class="sxs-lookup"><span data-stu-id="a9833-105">Members</span></span>  
  
|<span data-ttu-id="a9833-106">Член</span><span class="sxs-lookup"><span data-stu-id="a9833-106">Member</span></span>|<span data-ttu-id="a9833-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="a9833-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="a9833-108">Указывает, что среда CLR присоединит значения политики исходной сборки к соответствующим целевой сборки.</span><span class="sxs-lookup"><span data-stu-id="a9833-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="a9833-109">Указывает, что среда CLR выполняет действие по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a9833-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="a9833-110">Указывает, что среда CLR будет значения политики целевой сборки максимальные значения.</span><span class="sxs-lookup"><span data-stu-id="a9833-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="a9833-111">Указывает, что среда CLR заменит значения политики целевой сборки с этими исходной сборки.</span><span class="sxs-lookup"><span data-stu-id="a9833-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9833-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="a9833-112">Remarks</span></span>  
 <span data-ttu-id="a9833-113">[ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) метод принимает параметр типа `EHostBindingPolicyModifyFlags`.</span><span class="sxs-lookup"><span data-stu-id="a9833-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9833-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a9833-114">Requirements</span></span>  
 <span data-ttu-id="a9833-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9833-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9833-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a9833-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9833-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9833-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9833-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9833-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9833-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a9833-119">See Also</span></span>  
 [<span data-ttu-id="a9833-120">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a9833-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="a9833-121">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="a9833-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
