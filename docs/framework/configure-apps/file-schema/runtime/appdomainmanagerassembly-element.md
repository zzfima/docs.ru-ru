---
title: Элемент <appDomainManagerAssembly>
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 4c4ea35bff17a0e5188f26884e93cf77173a7df8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154435"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="4f4c1-102">\<appDomainManagerСборка> Элемент</span><span class="sxs-lookup"><span data-stu-id="4f4c1-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="4f4c1-103">Указывает сборку, предоставляющую диспетчер домена приложения для домена приложения, по умолчанию используемого в процессе.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
<span data-ttu-id="4f4c1-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f4c1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4f4c1-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f4c1-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="4f4c1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerСборка>**</span><span class="sxs-lookup"><span data-stu-id="4f4c1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f4c1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f4c1-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f4c1-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4f4c1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4f4c1-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f4c1-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4f4c1-110">Attributes</span></span>  
  
|<span data-ttu-id="4f4c1-111">attribute</span><span class="sxs-lookup"><span data-stu-id="4f4c1-111">Attribute</span></span>|<span data-ttu-id="4f4c1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4f4c1-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="4f4c1-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-113">Required attribute.</span></span> <span data-ttu-id="4f4c1-114">Упогоняет имя дисплея сборки, которая обеспечивает менеджер домена приложения для домена приложения по умолчанию в процессе.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f4c1-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4f4c1-115">Child Elements</span></span>  
 <span data-ttu-id="4f4c1-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f4c1-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4f4c1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4f4c1-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="4f4c1-118">Element</span></span>|<span data-ttu-id="4f4c1-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4f4c1-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4f4c1-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4f4c1-121">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f4c1-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="4f4c1-122">Remarks</span></span>  
 <span data-ttu-id="4f4c1-123">Чтобы указать тип менеджера домена приложения, необходимо указать как этот элемент, так и [ \<элемент appDomainManagerType>](appdomainmanagertype-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="4f4c1-124">Если какой-либо из этих элементов не указан, другой игнорируется.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="4f4c1-125">При загрузке домена приложения <xref:System.TypeLoadException> по умолчанию, выбрасывается, если указанная сборка не существует или если сборка не содержит тип, указанный [ \<элементом appDomainManagerType>;](appdomainmanagertype-element.md) и процесс не может начаться.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="4f4c1-126">Если сборка найдена, но информация <xref:System.IO.FileLoadException> о версии не совпадает, a брошена.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="4f4c1-127">При указании типа менеджера домена приложения для домена приложения по умолчанию другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип менеджера домена приложения.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="4f4c1-128">Используйте <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> и свойства, чтобы указать другой тип менеджера домена приложения для нового домена приложения.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="4f4c1-129">Определение типа диспетчера домена приложения требует, чтобы приложение было полностью доверчиво.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="4f4c1-130">(Например, приложение, работая на рабочем столе, имеет полное доверие.) Если приложение не имеет полного <xref:System.TypeLoadException> доверия, a брошен.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="4f4c1-131">Для формата названия отображения сборки см. <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4f4c1-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="4f4c1-132">Этот элемент конфигурации доступен только в системе .NET 4 и позже.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-132">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f4c1-133">Пример</span><span class="sxs-lookup"><span data-stu-id="4f4c1-133">Example</span></span>  
 <span data-ttu-id="4f4c1-134">В следующем примере показано, как указать, что менеджер домена `MyMgr` приложения `AdMgrExample` для домена приложения приложения по умолчанию процесса — это тип сборки.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f4c1-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4f4c1-135">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4f4c1-136">\<appDomainManagerType> Элемент</span><span class="sxs-lookup"><span data-stu-id="4f4c1-136">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="4f4c1-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="4f4c1-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4f4c1-138">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="4f4c1-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4f4c1-139">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="4f4c1-139">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
