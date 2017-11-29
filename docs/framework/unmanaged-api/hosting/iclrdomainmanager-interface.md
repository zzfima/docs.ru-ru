---
title: "Интерфейс ICLRDomainManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager
helpviewer_keywords: ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75a7e93d26a5c77484d78ad4632bedf8def6a44b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="7eb1d-102">Интерфейс ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="7eb1d-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="7eb1d-103">Ведущее приложение может указать диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также указать свойства инициализации.</span><span class="sxs-lookup"><span data-stu-id="7eb1d-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7eb1d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7eb1d-104">Methods</span></span>  
  
|<span data-ttu-id="7eb1d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7eb1d-105">Method</span></span>|<span data-ttu-id="7eb1d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7eb1d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7eb1d-107">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="7eb1d-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="7eb1d-108">Указывает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класса диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7eb1d-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="7eb1d-109">Setpropertiesfordefaultappdomain-метод</span><span class="sxs-lookup"><span data-stu-id="7eb1d-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="7eb1d-110">Задает свойства, которые будут использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7eb1d-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7eb1d-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="7eb1d-111">Remarks</span></span>  
 <span data-ttu-id="7eb1d-112">Чтобы получить экземпляр этого интерфейса, вызовите [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метода с типом manager IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="7eb1d-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eb1d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7eb1d-113">Requirements</span></span>  
 <span data-ttu-id="7eb1d-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eb1d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eb1d-115">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7eb1d-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7eb1d-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7eb1d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7eb1d-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eb1d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb1d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7eb1d-118">See Also</span></span>  
 [<span data-ttu-id="7eb1d-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="7eb1d-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="7eb1d-120">Размещение</span><span class="sxs-lookup"><span data-stu-id="7eb1d-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
