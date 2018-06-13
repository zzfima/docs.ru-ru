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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbcbc446eabcfcbc28c830f8860bde726c8eb6e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434772"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="4d4df-102">Интерфейс IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="4d4df-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="4d4df-103">Предоставляет свойства, позволяющие настроить узел <xref:System.AppDomain?displayProperty=nameWithType> тип перед вызовом [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) метод для его создания.</span><span class="sxs-lookup"><span data-stu-id="4d4df-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4d4df-104">Свойства</span><span class="sxs-lookup"><span data-stu-id="4d4df-104">Properties</span></span>  
  
|<span data-ttu-id="4d4df-105">Свойство</span><span class="sxs-lookup"><span data-stu-id="4d4df-105">Property</span></span>|<span data-ttu-id="4d4df-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4d4df-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="4d4df-107">Возвращает или задает имя каталога, содержащего приложение.</span><span class="sxs-lookup"><span data-stu-id="4d4df-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="4d4df-108">Возвращает или задает имя приложения.</span><span class="sxs-lookup"><span data-stu-id="4d4df-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="4d4df-109">Возвращает или задает имя области конкретных приложению где создаются теневые копии файлов.</span><span class="sxs-lookup"><span data-stu-id="4d4df-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="4d4df-110">Возвращает или задает имя файла конфигурации для приложения.</span><span class="sxs-lookup"><span data-stu-id="4d4df-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="4d4df-111">Возвращает или задает имя каталога, где сохраняются и становятся доступными динамически созданные файлы.</span><span class="sxs-lookup"><span data-stu-id="4d4df-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="4d4df-112">Возвращает или задает путь к файлу лицензии, связанного с этим доменом.</span><span class="sxs-lookup"><span data-stu-id="4d4df-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="4d4df-113">Возвращает или задает список каталогов, в сочетании с <xref:System.AppDomainSetup.ApplicationBase%2A> directory, чтобы производить поиск закрытых сборок.</span><span class="sxs-lookup"><span data-stu-id="4d4df-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="4d4df-114">Возвращает или задает строковое значение, которое включает или исключает <xref:System.AppDomainSetup.ApplicationBase%2A> из пути поиска для приложения.</span><span class="sxs-lookup"><span data-stu-id="4d4df-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="4d4df-115">Возвращает или задает имена каталогов, содержащих сборки, подлежащие теневому копированию.</span><span class="sxs-lookup"><span data-stu-id="4d4df-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="4d4df-116">Возвращает или задает строку, позволяющую определить, включено ли теневое копирование.</span><span class="sxs-lookup"><span data-stu-id="4d4df-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="4d4df-117">Допустимыми значениями являются «true» или «false».</span><span class="sxs-lookup"><span data-stu-id="4d4df-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d4df-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d4df-118">Remarks</span></span>  
 <span data-ttu-id="4d4df-119">`IAppDomainSetup` Соответствующий интерфейс в управляемом <xref:System.IAppDomainSetup> интерфейс, который <xref:System.AppDomainSetup> тип реализует.</span><span class="sxs-lookup"><span data-stu-id="4d4df-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="4d4df-120">В разделе <xref:System.IAppDomainSetup?displayProperty=nameWithType> подробные описания его свойств.</span><span class="sxs-lookup"><span data-stu-id="4d4df-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="4d4df-121">`IAppDomainSetup` Представляет сведения о привязке сборок, которые могут добавляться в <xref:System.AppDomain> экземпляра до его создания.</span><span class="sxs-lookup"><span data-stu-id="4d4df-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="4d4df-122">Например, хост может устанавливать <xref:System.AppDomainSetup.ApplicationBase%2A> свойства, чтобы установить корневой каталог, общеязыковой среды выполнения (CLR) проверяет наличие управляемых сборок.</span><span class="sxs-lookup"><span data-stu-id="4d4df-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d4df-123">Требования</span><span class="sxs-lookup"><span data-stu-id="4d4df-123">Requirements</span></span>  
 <span data-ttu-id="4d4df-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d4df-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d4df-125">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4d4df-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d4df-126">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4d4df-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d4df-127">**Версии платформы .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d4df-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d4df-128">См. также</span><span class="sxs-lookup"><span data-stu-id="4d4df-128">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup>  
 [<span data-ttu-id="4d4df-129">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4d4df-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
