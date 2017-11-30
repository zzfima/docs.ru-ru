---
title: "Перечисление EInitializeNewDomainFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EInitializeNewDomainFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: EInitializeNewDomainFlags
helpviewer_keywords: EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bee1c5086502a9675e8149e7d6c9bc72f573815c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="6a698-102">Перечисление EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="6a698-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="6a698-103">Ведущее приложение может предоставлять среде выполнения сведения об инициализации домена приложения.</span><span class="sxs-lookup"><span data-stu-id="6a698-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a698-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a698-104">Syntax</span></span>  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6a698-105">Члены</span><span class="sxs-lookup"><span data-stu-id="6a698-105">Members</span></span>  
  
|<span data-ttu-id="6a698-106">Член</span><span class="sxs-lookup"><span data-stu-id="6a698-106">Member</span></span>|<span data-ttu-id="6a698-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6a698-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="6a698-108">Флаги не.</span><span class="sxs-lookup"><span data-stu-id="6a698-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="6a698-109">Информирует общеязыковой среды выполнения (CLR), что узел не внесет изменений в состояние безопасности домена приложения в <xref:System.AppDomainManager.InitializeNewDomain%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="6a698-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a698-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6a698-110">Remarks</span></span>  
 <span data-ttu-id="6a698-111">[ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) метод принимает параметр типа `EInitializeNewDomainFlags`.</span><span class="sxs-lookup"><span data-stu-id="6a698-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a698-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6a698-112">Requirements</span></span>  
 <span data-ttu-id="6a698-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a698-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a698-114">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6a698-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a698-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a698-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a698-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a698-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a698-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6a698-117">See Also</span></span>  
 [<span data-ttu-id="6a698-118">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="6a698-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="6a698-119">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="6a698-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
