---
title: Перечисление EInitializeNewDomainFlags
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04b0d9989d66888c33de0359e4c93529fcfbf8d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628630"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="abb18-102">Перечисление EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="abb18-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="abb18-103">Ведущее приложение может предоставлять среде выполнения сведения об инициализации домена приложения.</span><span class="sxs-lookup"><span data-stu-id="abb18-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abb18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abb18-104">Syntax</span></span>  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="abb18-105">Участники</span><span class="sxs-lookup"><span data-stu-id="abb18-105">Members</span></span>  
  
|<span data-ttu-id="abb18-106">Член</span><span class="sxs-lookup"><span data-stu-id="abb18-106">Member</span></span>|<span data-ttu-id="abb18-107">Описание</span><span class="sxs-lookup"><span data-stu-id="abb18-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="abb18-108">Флаги отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="abb18-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="abb18-109">Информирует общеязыковой среды выполнения (CLR) о том, что узел не будет вносить изменения в состояние безопасности домена приложения в <xref:System.AppDomainManager.InitializeNewDomain%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="abb18-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abb18-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="abb18-110">Remarks</span></span>  
 <span data-ttu-id="abb18-111">[ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) метод принимает параметр типа `EInitializeNewDomainFlags`.</span><span class="sxs-lookup"><span data-stu-id="abb18-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abb18-112">Требования</span><span class="sxs-lookup"><span data-stu-id="abb18-112">Requirements</span></span>  
 <span data-ttu-id="abb18-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abb18-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abb18-114">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="abb18-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="abb18-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="abb18-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abb18-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abb18-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abb18-117">См. также</span><span class="sxs-lookup"><span data-stu-id="abb18-117">See also</span></span>

- [<span data-ttu-id="abb18-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="abb18-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="abb18-119">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="abb18-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
