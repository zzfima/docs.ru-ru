---
title: Интерфейс ICLRDomainManager
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce53149b92ca40ad50ecbefaf4701940e8567ae5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984754"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="e4a35-102">Интерфейс ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="e4a35-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="e4a35-103">Ведущее приложение может указать диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также для указания свойств инициализации.</span><span class="sxs-lookup"><span data-stu-id="e4a35-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4a35-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e4a35-104">Methods</span></span>  
  
|<span data-ttu-id="e4a35-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e4a35-105">Method</span></span>|<span data-ttu-id="e4a35-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e4a35-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4a35-107">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="e4a35-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="e4a35-108">Указывает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класс диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e4a35-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="e4a35-109">Метод SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="e4a35-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="e4a35-110">Задает свойства, которые будут использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e4a35-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4a35-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4a35-111">Remarks</span></span>  
 <span data-ttu-id="e4a35-112">Чтобы получить экземпляр этого интерфейса, вызовите [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метод с типом manager IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="e4a35-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4a35-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e4a35-113">Requirements</span></span>  
 <span data-ttu-id="e4a35-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4a35-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4a35-115">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e4a35-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e4a35-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e4a35-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4a35-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4a35-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4a35-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e4a35-118">See also</span></span>

- [<span data-ttu-id="e4a35-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e4a35-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="e4a35-120">Размещение</span><span class="sxs-lookup"><span data-stu-id="e4a35-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
