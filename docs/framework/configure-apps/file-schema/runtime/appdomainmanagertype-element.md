---
title: '&lt;appDomainManagerType&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e7f37fd652ce98e24d2e2e99edcd3d59a0e597b
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610436"
---
# <a name="ltappdomainmanagertypegt-element"></a><span data-ttu-id="20928-102">&lt;appDomainManagerType&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="20928-102">&lt;appDomainManagerType&gt; Element</span></span>
<span data-ttu-id="20928-103">Указывает тип, который служит диспетчером домена приложения для домена приложения, используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="20928-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
 <span data-ttu-id="20928-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="20928-104">\<configuration></span></span>  
<span data-ttu-id="20928-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="20928-105">\<runtime></span></span>  
<span data-ttu-id="20928-106">\<appDomainManagerType ></span><span class="sxs-lookup"><span data-stu-id="20928-106">\<appDomainManagerType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20928-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20928-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20928-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="20928-108">Attributes and Elements</span></span>  
 <span data-ttu-id="20928-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="20928-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20928-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="20928-110">Attributes</span></span>  
  
|<span data-ttu-id="20928-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="20928-111">Attribute</span></span>|<span data-ttu-id="20928-112">Описание</span><span class="sxs-lookup"><span data-stu-id="20928-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="20928-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="20928-113">Required attribute.</span></span> <span data-ttu-id="20928-114">Задает имя типа, включая пространство имен, который служит в качестве домена приложения для домена приложения по умолчанию в процессе.</span><span class="sxs-lookup"><span data-stu-id="20928-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20928-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="20928-115">Child Elements</span></span>  
 <span data-ttu-id="20928-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="20928-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20928-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="20928-117">Parent Elements</span></span>  
  
|<span data-ttu-id="20928-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="20928-118">Element</span></span>|<span data-ttu-id="20928-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="20928-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="20928-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20928-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="20928-121">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="20928-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20928-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="20928-122">Remarks</span></span>  
 <span data-ttu-id="20928-123">Чтобы задать тип диспетчера доменов приложений, необходимо задать как этот элемент и [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="20928-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="20928-124">Если один из этих элементов не указан, то другое обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="20928-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="20928-125">При загрузке домена приложения по умолчанию <xref:System.TypeLoadException> возникает исключение, если указанный тип не существует в сборке, который задается параметром [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) элемент; и процесс завершится сбоем, чтобы Начало.</span><span class="sxs-lookup"><span data-stu-id="20928-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="20928-126">Если указать тип диспетчера домена приложения для домена приложения по умолчанию, других доменов приложений, созданных из домена приложения по умолчанию наследуют тип диспетчера домена приложения.</span><span class="sxs-lookup"><span data-stu-id="20928-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="20928-127">Используйте <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> и <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> свойства для указания типа диспетчера домена приложения в новом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="20928-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="20928-128">Требуется указать тип диспетчера домена приложения, приложение полного доверия.</span><span class="sxs-lookup"><span data-stu-id="20928-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="20928-129">(Например, приложения, работающего на рабочем столе имеет полное доверие). Если приложение не имеет полного доверия, <xref:System.TypeLoadException> возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="20928-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="20928-130">Формат типа и пространство имен — это тот же формат, который используется для <xref:System.Type.FullName%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="20928-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="20928-131">Этот элемент конфигурации доступен только в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="20928-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20928-132">Пример</span><span class="sxs-lookup"><span data-stu-id="20928-132">Example</span></span>  
 <span data-ttu-id="20928-133">В следующем примере показано, как указать, что диспетчер домена приложения для домена приложения по умолчанию процесса `MyMgr` введите `AdMgrExample` сборки.</span><span class="sxs-lookup"><span data-stu-id="20928-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="20928-134">См. также</span><span class="sxs-lookup"><span data-stu-id="20928-134">See Also</span></span>  
- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="20928-135">\<appDomainManagerAssembly > элемент</span><span class="sxs-lookup"><span data-stu-id="20928-135">\<appDomainManagerAssembly> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
- [<span data-ttu-id="20928-136">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="20928-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="20928-137">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="20928-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="20928-138">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="20928-138">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
