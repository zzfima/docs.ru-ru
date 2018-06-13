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
ms.openlocfilehash: c3b8dd67cb7dff4bec5bab192a08461ef13fcbd9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436362"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="81456-102">Интерфейс ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="81456-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="81456-103">Ведущее приложение может указать диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также указать свойства инициализации.</span><span class="sxs-lookup"><span data-stu-id="81456-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81456-104">Методы</span><span class="sxs-lookup"><span data-stu-id="81456-104">Methods</span></span>  
  
|<span data-ttu-id="81456-105">Метод</span><span class="sxs-lookup"><span data-stu-id="81456-105">Method</span></span>|<span data-ttu-id="81456-106">Описание</span><span class="sxs-lookup"><span data-stu-id="81456-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81456-107">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="81456-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="81456-108">Указывает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класса диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="81456-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="81456-109">Метод SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="81456-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="81456-110">Задает свойства, которые будут использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="81456-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81456-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="81456-111">Remarks</span></span>  
 <span data-ttu-id="81456-112">Чтобы получить экземпляр этого интерфейса, вызовите [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метода с типом manager IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="81456-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81456-113">Требования</span><span class="sxs-lookup"><span data-stu-id="81456-113">Requirements</span></span>  
 <span data-ttu-id="81456-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81456-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81456-115">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="81456-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="81456-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="81456-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81456-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81456-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81456-118">См. также</span><span class="sxs-lookup"><span data-stu-id="81456-118">See Also</span></span>  
 [<span data-ttu-id="81456-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="81456-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="81456-120">Размещение</span><span class="sxs-lookup"><span data-stu-id="81456-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
