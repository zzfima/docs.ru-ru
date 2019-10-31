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
ms.openlocfilehash: aa874205cf14232e7a69ed2215086e33c0beab4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129344"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="37f91-102">Интерфейс ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="37f91-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="37f91-103">Позволяет узлу указать Диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также для указания свойств инициализации.</span><span class="sxs-lookup"><span data-stu-id="37f91-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37f91-104">Методы</span><span class="sxs-lookup"><span data-stu-id="37f91-104">Methods</span></span>  
  
|<span data-ttu-id="37f91-105">Метод</span><span class="sxs-lookup"><span data-stu-id="37f91-105">Method</span></span>|<span data-ttu-id="37f91-106">Описание</span><span class="sxs-lookup"><span data-stu-id="37f91-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37f91-107">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="37f91-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="37f91-108">Задает тип, производный от класса <xref:System.AppDomainManager?displayProperty=nameWithType> диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37f91-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="37f91-109">Метод SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="37f91-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="37f91-110">Задает свойства, которые будут использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37f91-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37f91-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="37f91-111">Remarks</span></span>  
 <span data-ttu-id="37f91-112">Чтобы получить экземпляр этого интерфейса, вызовите метод [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) с типом менеджера IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="37f91-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37f91-113">Требования</span><span class="sxs-lookup"><span data-stu-id="37f91-113">Requirements</span></span>  
 <span data-ttu-id="37f91-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37f91-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37f91-115">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="37f91-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="37f91-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="37f91-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37f91-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37f91-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37f91-118">См. также</span><span class="sxs-lookup"><span data-stu-id="37f91-118">See also</span></span>

- [<span data-ttu-id="37f91-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="37f91-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="37f91-120">Размещение</span><span class="sxs-lookup"><span data-stu-id="37f91-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
