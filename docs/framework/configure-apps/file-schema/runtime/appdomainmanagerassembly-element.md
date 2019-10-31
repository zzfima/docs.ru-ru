---
title: Элемент <appDomainManagerAssembly>
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 7ba52cdf0102af05954509a11fa90e9b8a337876
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118321"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="3cb8a-102">\<Аппдомаинманажерассембли > элемент</span><span class="sxs-lookup"><span data-stu-id="3cb8a-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="3cb8a-103">Указывает сборку, предоставляющую диспетчер домена приложения для домена приложения, по умолчанию используемого в процессе.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
<span data-ttu-id="3cb8a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3cb8a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3cb8a-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="3cb8a-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3cb8a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<аппдомаинманажерассембли >**</span><span class="sxs-lookup"><span data-stu-id="3cb8a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cb8a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cb8a-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cb8a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3cb8a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3cb8a-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cb8a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3cb8a-110">Attributes</span></span>  
  
|<span data-ttu-id="3cb8a-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3cb8a-111">Attribute</span></span>|<span data-ttu-id="3cb8a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3cb8a-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="3cb8a-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-113">Required attribute.</span></span> <span data-ttu-id="3cb8a-114">Указывает отображаемое имя сборки, предоставляющей Диспетчер доменов приложений для домена приложения по умолчанию в процессе.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cb8a-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3cb8a-115">Child Elements</span></span>  
 <span data-ttu-id="3cb8a-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cb8a-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3cb8a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3cb8a-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="3cb8a-118">Element</span></span>|<span data-ttu-id="3cb8a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3cb8a-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3cb8a-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3cb8a-121">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cb8a-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="3cb8a-122">Remarks</span></span>  
 <span data-ttu-id="3cb8a-123">Чтобы указать тип диспетчера домена приложения, необходимо указать и этот элемент, и элемент [\<аппдомаинманажертипе >](appdomainmanagertype-element.md) .</span><span class="sxs-lookup"><span data-stu-id="3cb8a-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="3cb8a-124">Если один из этих элементов не указан, другой игнорируется.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="3cb8a-125">При загрузке домена приложения по умолчанию <xref:System.TypeLoadException> создается, если указанная сборка не существует или если сборка не содержит тип, указанный в элементе [\<аппдомаинманажертипе >](appdomainmanagertype-element.md) . и процесс не запускается.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="3cb8a-126">Если сборка найдена, но сведения о версии не совпадают, создается <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="3cb8a-127">При указании типа диспетчера домена приложения для домена приложения по умолчанию другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип диспетчера домена приложения.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="3cb8a-128">Используйте свойства <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> и <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>, чтобы указать другой тип диспетчера домена приложения для нового домена приложения.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="3cb8a-129">Чтобы указать тип диспетчера доменов приложений, приложение должно иметь полное доверие.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="3cb8a-130">(Например, приложение, работающее на рабочем столе, имеет полное доверие.) Если приложение не имеет полного доверия, выдается <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="3cb8a-131">Сведения о формате отображаемого имени сборки см. в описании свойства <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="3cb8a-132">Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-132">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cb8a-133">Пример</span><span class="sxs-lookup"><span data-stu-id="3cb8a-133">Example</span></span>  
 <span data-ttu-id="3cb8a-134">В следующем примере показано, как указать, что диспетчер домена приложения для домена приложения по умолчанию процесса является типом `MyMgr` в сборке `AdMgrExample`.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cb8a-135">См. также</span><span class="sxs-lookup"><span data-stu-id="3cb8a-135">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3cb8a-136">\<Аппдомаинманажертипе > элемент</span><span class="sxs-lookup"><span data-stu-id="3cb8a-136">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="3cb8a-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="3cb8a-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3cb8a-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="3cb8a-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3cb8a-139">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="3cb8a-139">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
