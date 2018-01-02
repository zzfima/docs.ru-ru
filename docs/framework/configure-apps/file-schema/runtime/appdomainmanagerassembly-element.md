---
title: "&lt;appDomainManagerAssembly&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52e09e898fdcdbf8d14d3648b19e40bdc302daf0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltappdomainmanagerassemblygt-element"></a><span data-ttu-id="311f2-102">&lt;appDomainManagerAssembly&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="311f2-102">&lt;appDomainManagerAssembly&gt; Element</span></span>
<span data-ttu-id="311f2-103">Указывает сборку, предоставляющую диспетчер домена приложения для домена приложения, по умолчанию используемого в процессе.</span><span class="sxs-lookup"><span data-stu-id="311f2-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
 <span data-ttu-id="311f2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="311f2-104">\<configuration></span></span>  
<span data-ttu-id="311f2-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="311f2-105">\<runtime></span></span>  
<span data-ttu-id="311f2-106">\<appDomainManagerAssembly ></span><span class="sxs-lookup"><span data-stu-id="311f2-106">\<appDomainManagerAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="311f2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="311f2-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="311f2-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="311f2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="311f2-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="311f2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="311f2-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="311f2-110">Attributes</span></span>  
  
|<span data-ttu-id="311f2-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="311f2-111">Attribute</span></span>|<span data-ttu-id="311f2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="311f2-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="311f2-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="311f2-113">Required attribute.</span></span> <span data-ttu-id="311f2-114">Указывает отображаемое имя сборки, предоставляющей диспетчер домена приложения для домена приложения по умолчанию в процессе.</span><span class="sxs-lookup"><span data-stu-id="311f2-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="311f2-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="311f2-115">Child Elements</span></span>  
 <span data-ttu-id="311f2-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="311f2-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="311f2-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="311f2-117">Parent Elements</span></span>  
  
|<span data-ttu-id="311f2-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="311f2-118">Element</span></span>|<span data-ttu-id="311f2-119">Описание</span><span class="sxs-lookup"><span data-stu-id="311f2-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="311f2-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="311f2-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="311f2-121">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="311f2-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="311f2-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="311f2-122">Remarks</span></span>  
 <span data-ttu-id="311f2-123">Чтобы задать тип диспетчера домена приложения, необходимо задать как этот элемент и [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="311f2-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="311f2-124">Если один из этих элементов не задан, другой игнорируется.</span><span class="sxs-lookup"><span data-stu-id="311f2-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="311f2-125">При загрузке домена приложения по умолчанию <xref:System.TypeLoadException> выдается, если указанная сборка не существует или если сборка не содержит тип, заданный параметром [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) элементу; и не удается запустить процесс.</span><span class="sxs-lookup"><span data-stu-id="311f2-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="311f2-126">Если сборка найдена, но сведения о версии не совпадают, <xref:System.IO.FileLoadException> возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="311f2-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="311f2-127">Если указать тип диспетчера домена приложения для домена приложения по умолчанию, другие домены приложений, созданные на основе домена приложения по умолчанию наследуют тип диспетчера домена приложения.</span><span class="sxs-lookup"><span data-stu-id="311f2-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="311f2-128">Используйте <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> и <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> свойства, чтобы указать тип диспетчера домена приложения в новом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="311f2-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="311f2-129">Определяющее тип диспетчера домена приложения требует полного доверия приложения.</span><span class="sxs-lookup"><span data-stu-id="311f2-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="311f2-130">(Например, приложения, работающего на рабочем столе имеет полное доверие). Если приложение не имеет полного доверия <xref:System.TypeLoadException> возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="311f2-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="311f2-131">Формат выводимого имени сборки, в разделе <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="311f2-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="311f2-132">Этот элемент конфигурации доступен только в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="311f2-132">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="311f2-133">Пример</span><span class="sxs-lookup"><span data-stu-id="311f2-133">Example</span></span>  
 <span data-ttu-id="311f2-134">В следующем примере показано, как указать, что диспетчер домена приложения для домена приложения по умолчанию процесса `MyMgr` введите `AdMgrExample` сборки.</span><span class="sxs-lookup"><span data-stu-id="311f2-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="311f2-135">См. также</span><span class="sxs-lookup"><span data-stu-id="311f2-135">See Also</span></span>  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="311f2-136">\<appDomainManagerType > элемент</span><span class="sxs-lookup"><span data-stu-id="311f2-136">\<appDomainManagerType> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)  
 [<span data-ttu-id="311f2-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="311f2-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="311f2-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="311f2-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="311f2-139">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="311f2-139">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
