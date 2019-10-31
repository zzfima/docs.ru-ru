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
ms.openlocfilehash: a2faf22b48dd0b809d6c3668a37f2119733a9b18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129448"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="b0b6b-102">Перечисление EHostBindingPolicyModifyFlags</span><span class="sxs-lookup"><span data-stu-id="b0b6b-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="b0b6b-103">Позволяет узлу указать тип перенаправления, которое должна выполнять среда CLR при применении изменений политики из исходной сборки к целевой сборке.</span><span class="sxs-lookup"><span data-stu-id="b0b6b-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0b6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0b6b-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b0b6b-105">Члены</span><span class="sxs-lookup"><span data-stu-id="b0b6b-105">Members</span></span>  
  
|<span data-ttu-id="b0b6b-106">Член</span><span class="sxs-lookup"><span data-stu-id="b0b6b-106">Member</span></span>|<span data-ttu-id="b0b6b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b0b6b-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="b0b6b-108">Указывает, что среда CLR будет связывать значения политики исходной сборки с целевыми сборками.</span><span class="sxs-lookup"><span data-stu-id="b0b6b-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="b0b6b-109">Указывает, что среда CLR будет выполнять действие по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b0b6b-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="b0b6b-110">Указывает, что среда CLR будет задавать максимальные значения политики для целевой сборки.</span><span class="sxs-lookup"><span data-stu-id="b0b6b-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="b0b6b-111">Указывает, что среда CLR заменит значения политики целевой сборки значениями из исходной сборки.</span><span class="sxs-lookup"><span data-stu-id="b0b6b-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0b6b-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="b0b6b-112">Remarks</span></span>  
 <span data-ttu-id="b0b6b-113">Метод [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) принимает параметр типа `EHostBindingPolicyModifyFlags`.</span><span class="sxs-lookup"><span data-stu-id="b0b6b-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0b6b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b0b6b-114">Requirements</span></span>  
 <span data-ttu-id="b0b6b-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0b6b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0b6b-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b0b6b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0b6b-117">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b0b6b-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0b6b-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0b6b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0b6b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b0b6b-119">See also</span></span>

- [<span data-ttu-id="b0b6b-120">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="b0b6b-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="b0b6b-121">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="b0b6b-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
