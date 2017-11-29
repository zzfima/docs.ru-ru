---
title: "&lt;appDomainManagerType&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 56d68efe176540ba82ec7b86f35678905ebc970b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltappdomainmanagertypegt-element"></a><span data-ttu-id="fea80-102">&lt;appDomainManagerType&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="fea80-102">&lt;appDomainManagerType&gt; Element</span></span>
<span data-ttu-id="fea80-103">Указывает тип, который служит диспетчером домена приложения для домена приложения, используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fea80-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
 <span data-ttu-id="fea80-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fea80-104">\<configuration></span></span>  
<span data-ttu-id="fea80-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="fea80-105">\<runtime></span></span>  
<span data-ttu-id="fea80-106">\<appDomainManagerType ></span><span class="sxs-lookup"><span data-stu-id="fea80-106">\<appDomainManagerType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fea80-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fea80-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fea80-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fea80-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fea80-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fea80-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fea80-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fea80-110">Attributes</span></span>  
  
|<span data-ttu-id="fea80-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fea80-111">Attribute</span></span>|<span data-ttu-id="fea80-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fea80-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="fea80-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="fea80-113">Required attribute.</span></span> <span data-ttu-id="fea80-114">Задает имя типа, включая пространство имен, которая служит диспетчер домена приложения для домена приложения по умолчанию в процессе.</span><span class="sxs-lookup"><span data-stu-id="fea80-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fea80-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fea80-115">Child Elements</span></span>  
 <span data-ttu-id="fea80-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fea80-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fea80-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fea80-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fea80-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="fea80-118">Element</span></span>|<span data-ttu-id="fea80-119">Описание</span><span class="sxs-lookup"><span data-stu-id="fea80-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fea80-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fea80-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fea80-121">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="fea80-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fea80-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="fea80-122">Remarks</span></span>  
 <span data-ttu-id="fea80-123">Чтобы задать тип диспетчера домена приложения, необходимо задать как этот элемент и [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="fea80-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="fea80-124">Если один из этих элементов не задан, другой игнорируется.</span><span class="sxs-lookup"><span data-stu-id="fea80-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="fea80-125">При загрузке домена приложения по умолчанию <xref:System.TypeLoadException> создается, если указанный тип не существует в сборке, которая определяется [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) элементу; и завершилось неудачно для Начало.</span><span class="sxs-lookup"><span data-stu-id="fea80-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="fea80-126">Если указать тип диспетчера домена приложения для домена приложения по умолчанию, другие домены приложений, созданные на основе домена приложения по умолчанию наследуют тип диспетчера домена приложения.</span><span class="sxs-lookup"><span data-stu-id="fea80-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="fea80-127">Используйте <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> и <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> свойства, чтобы указать тип диспетчера домена приложения в новом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="fea80-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="fea80-128">Определяющее тип диспетчера домена приложения требует полного доверия приложения.</span><span class="sxs-lookup"><span data-stu-id="fea80-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="fea80-129">(Например, приложения, работающего на рабочем столе имеет полное доверие). Если приложение не имеет полного доверия <xref:System.TypeLoadException> возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="fea80-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="fea80-130">Формат типа и пространство имен имеет тот же формат, используемый для <xref:System.Type.FullName%2A?displayProperty=nameWithType> свойства.</span><span class="sxs-lookup"><span data-stu-id="fea80-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="fea80-131">Этот элемент конфигурации доступен только в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="fea80-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fea80-132">Пример</span><span class="sxs-lookup"><span data-stu-id="fea80-132">Example</span></span>  
 <span data-ttu-id="fea80-133">В следующем примере показано, как указать, что диспетчер домена приложения для домена приложения по умолчанию процесса `MyMgr` введите `AdMgrExample` сборки.</span><span class="sxs-lookup"><span data-stu-id="fea80-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fea80-134">См. также</span><span class="sxs-lookup"><span data-stu-id="fea80-134">See Also</span></span>  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="fea80-135">\<appDomainManagerAssembly > элемент</span><span class="sxs-lookup"><span data-stu-id="fea80-135">\<appDomainManagerAssembly> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
 [<span data-ttu-id="fea80-136">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="fea80-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="fea80-137">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="fea80-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="fea80-138">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="fea80-138">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
