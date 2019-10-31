---
title: Элемент <appDomainManagerType>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: bae4aa39f9c43480ac2ef984f78834b68646742d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118245"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="384b4-102">\<Аппдомаинманажертипе > элемент</span><span class="sxs-lookup"><span data-stu-id="384b4-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="384b4-103">Указывает тип, который служит диспетчером домена приложения для домена приложения, используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="384b4-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
<span data-ttu-id="384b4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="384b4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="384b4-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="384b4-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="384b4-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<аппдомаинманажертипе >**</span><span class="sxs-lookup"><span data-stu-id="384b4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="384b4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="384b4-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="384b4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="384b4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="384b4-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="384b4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="384b4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="384b4-110">Attributes</span></span>  
  
|<span data-ttu-id="384b4-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="384b4-111">Attribute</span></span>|<span data-ttu-id="384b4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="384b4-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="384b4-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="384b4-113">Required attribute.</span></span> <span data-ttu-id="384b4-114">Указывает имя типа, включая пространство имен, которое служит диспетчером доменов приложений для домена приложения по умолчанию в процессе.</span><span class="sxs-lookup"><span data-stu-id="384b4-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="384b4-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="384b4-115">Child Elements</span></span>  
 <span data-ttu-id="384b4-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="384b4-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="384b4-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="384b4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="384b4-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="384b4-118">Element</span></span>|<span data-ttu-id="384b4-119">Описание</span><span class="sxs-lookup"><span data-stu-id="384b4-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="384b4-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="384b4-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="384b4-121">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="384b4-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="384b4-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="384b4-122">Remarks</span></span>  
 <span data-ttu-id="384b4-123">Чтобы указать тип диспетчера домена приложения, необходимо указать и этот элемент, и элемент [\<аппдомаинманажерассембли >](appdomainmanagerassembly-element.md) .</span><span class="sxs-lookup"><span data-stu-id="384b4-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="384b4-124">Если один из этих элементов не указан, другой игнорируется.</span><span class="sxs-lookup"><span data-stu-id="384b4-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="384b4-125">При загрузке домена приложения по умолчанию <xref:System.TypeLoadException> вызывается, если указанный тип не существует в сборке, указанной в элементе [\<аппдомаинманажерассембли >](appdomainmanagerassembly-element.md) . и процесс не запускается.</span><span class="sxs-lookup"><span data-stu-id="384b4-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="384b4-126">При указании типа диспетчера домена приложения для домена приложения по умолчанию другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип диспетчера домена приложения.</span><span class="sxs-lookup"><span data-stu-id="384b4-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="384b4-127">Используйте свойства <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> и <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>, чтобы указать другой тип диспетчера домена приложения для нового домена приложения.</span><span class="sxs-lookup"><span data-stu-id="384b4-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="384b4-128">Чтобы указать тип диспетчера доменов приложений, приложение должно иметь полное доверие.</span><span class="sxs-lookup"><span data-stu-id="384b4-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="384b4-129">(Например, приложение, работающее на рабочем столе, имеет полное доверие.) Если приложение не имеет полного доверия, выдается <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="384b4-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="384b4-130">Формат типа и пространства имен совпадает с форматом, используемым для свойства <xref:System.Type.FullName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="384b4-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="384b4-131">Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="384b4-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="384b4-132">Пример</span><span class="sxs-lookup"><span data-stu-id="384b4-132">Example</span></span>  
 <span data-ttu-id="384b4-133">В следующем примере показано, как указать, что диспетчер домена приложения для домена приложения по умолчанию процесса является типом `MyMgr` в сборке `AdMgrExample`.</span><span class="sxs-lookup"><span data-stu-id="384b4-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="384b4-134">См. также</span><span class="sxs-lookup"><span data-stu-id="384b4-134">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="384b4-135">\<Аппдомаинманажерассембли > элемент</span><span class="sxs-lookup"><span data-stu-id="384b4-135">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="384b4-136">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="384b4-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="384b4-137">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="384b4-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="384b4-138">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="384b4-138">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
