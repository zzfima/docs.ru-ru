---
title: Перечисление EHostBindingPolicyModifyFlags
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d70f7dd872cefbadce56c577ce2ecc9cbcb663b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765847"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="e1b80-102">Перечисление EHostBindingPolicyModifyFlags</span><span class="sxs-lookup"><span data-stu-id="e1b80-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="e1b80-103">Позволяет узлу указать тип перенаправления, которые общеязыковой среды выполнения (CLR) следует выполнять при применении изменений политики из исходной сборки на целевую сборку.</span><span class="sxs-lookup"><span data-stu-id="e1b80-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1b80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1b80-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e1b80-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e1b80-105">Members</span></span>  
  
|<span data-ttu-id="e1b80-106">Член</span><span class="sxs-lookup"><span data-stu-id="e1b80-106">Member</span></span>|<span data-ttu-id="e1b80-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e1b80-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="e1b80-108">Указывает, что среда CLR присоединит значения политики исходной сборки к соответствующим целевой сборки.</span><span class="sxs-lookup"><span data-stu-id="e1b80-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="e1b80-109">Указывает, что среда CLR будет выполнять действие по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e1b80-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="e1b80-110">Указывает, что среда CLR установит значения политики целевой сборки максимальные значения.</span><span class="sxs-lookup"><span data-stu-id="e1b80-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="e1b80-111">Указывает, что среда CLR заменит значения политики целевой сборки с соответствующими исходной сборки.</span><span class="sxs-lookup"><span data-stu-id="e1b80-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1b80-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1b80-112">Remarks</span></span>  
 <span data-ttu-id="e1b80-113">[ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) метод принимает параметр типа `EHostBindingPolicyModifyFlags`.</span><span class="sxs-lookup"><span data-stu-id="e1b80-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1b80-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e1b80-114">Requirements</span></span>  
 <span data-ttu-id="e1b80-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1b80-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1b80-116">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e1b80-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1b80-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e1b80-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1b80-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1b80-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1b80-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e1b80-119">See also</span></span>

- [<span data-ttu-id="e1b80-120">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="e1b80-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="e1b80-121">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="e1b80-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
