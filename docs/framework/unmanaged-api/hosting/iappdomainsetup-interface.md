---
title: Интерфейс IAppDomainSetup
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
ms.openlocfilehash: 0fab64c31d4a73995c16d21767f4569f21c7df9a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126876"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="d44e5-102">Интерфейс IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="d44e5-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="d44e5-103">Предоставляет свойства, позволяющие узлу настроить тип <xref:System.AppDomain?displayProperty=nameWithType> перед вызовом метода [ICorRuntimeHost:: CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) для его создания.</span><span class="sxs-lookup"><span data-stu-id="d44e5-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d44e5-104">Свойства</span><span class="sxs-lookup"><span data-stu-id="d44e5-104">Properties</span></span>  
  
|<span data-ttu-id="d44e5-105">свойство;</span><span class="sxs-lookup"><span data-stu-id="d44e5-105">Property</span></span>|<span data-ttu-id="d44e5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d44e5-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="d44e5-107">Возвращает или задает имя каталога, содержащего приложение.</span><span class="sxs-lookup"><span data-stu-id="d44e5-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="d44e5-108">Возвращает или задает имя приложения.</span><span class="sxs-lookup"><span data-stu-id="d44e5-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="d44e5-109">Возвращает или задает имя области, относящейся к приложению, в котором файлы копируются при теневом копировании.</span><span class="sxs-lookup"><span data-stu-id="d44e5-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="d44e5-110">Возвращает или задает имя файла конфигурации для приложения.</span><span class="sxs-lookup"><span data-stu-id="d44e5-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="d44e5-111">Возвращает или задает имя каталога, в котором хранятся и обращаются динамически создаваемые файлы.</span><span class="sxs-lookup"><span data-stu-id="d44e5-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="d44e5-112">Возвращает или задает путь к файлу лицензии, связанному с этим доменом.</span><span class="sxs-lookup"><span data-stu-id="d44e5-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="d44e5-113">Возвращает или задает список каталогов в сочетании с каталогом <xref:System.AppDomainSetup.ApplicationBase%2A> для проверки закрытых сборок.</span><span class="sxs-lookup"><span data-stu-id="d44e5-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="d44e5-114">Возвращает или задает строковое значение, включающее или исключающее <xref:System.AppDomainSetup.ApplicationBase%2A> из пути поиска для приложения.</span><span class="sxs-lookup"><span data-stu-id="d44e5-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="d44e5-115">Возвращает или задает имена каталогов, содержащих сборки для теневого копирования.</span><span class="sxs-lookup"><span data-stu-id="d44e5-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="d44e5-116">Возвращает или задает строку, которая указывает, включено ли теневое копирование.</span><span class="sxs-lookup"><span data-stu-id="d44e5-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="d44e5-117">Допустимые значения: "true" или "false".</span><span class="sxs-lookup"><span data-stu-id="d44e5-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d44e5-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="d44e5-118">Remarks</span></span>  
 <span data-ttu-id="d44e5-119">Интерфейс `IAppDomainSetup` соответствует управляемому интерфейсу <xref:System.IAppDomainSetup>, который реализуется типом <xref:System.AppDomainSetup>.</span><span class="sxs-lookup"><span data-stu-id="d44e5-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="d44e5-120">Подробное описание его свойств см. в разделе <xref:System.IAppDomainSetup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d44e5-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="d44e5-121">`IAppDomainSetup` представляет сведения о привязке сборки, которые можно добавить в экземпляр <xref:System.AppDomain> перед его созданием.</span><span class="sxs-lookup"><span data-stu-id="d44e5-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="d44e5-122">Например, узел может задать свойство <xref:System.AppDomainSetup.ApplicationBase%2A>, чтобы установить корневой каталог, который проверяется средой CLR для управляемых сборок.</span><span class="sxs-lookup"><span data-stu-id="d44e5-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d44e5-123">Требования</span><span class="sxs-lookup"><span data-stu-id="d44e5-123">Requirements</span></span>  
 <span data-ttu-id="d44e5-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d44e5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d44e5-125">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d44e5-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d44e5-126">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d44e5-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d44e5-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d44e5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44e5-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d44e5-128">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [<span data-ttu-id="d44e5-129">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="d44e5-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
