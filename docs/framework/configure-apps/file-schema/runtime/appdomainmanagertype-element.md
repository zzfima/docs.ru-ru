---
title: Элемент <appDomainManagerType>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154434"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="db91c-102">\<appDomainManagerType> Элемент</span><span class="sxs-lookup"><span data-stu-id="db91c-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="db91c-103">Указывает тип, который служит диспетчером домена приложения для домена приложения, используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db91c-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
<span data-ttu-id="db91c-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="db91c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="db91c-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="db91c-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="db91c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span><span class="sxs-lookup"><span data-stu-id="db91c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db91c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db91c-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db91c-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="db91c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="db91c-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="db91c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db91c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="db91c-110">Attributes</span></span>  
  
|<span data-ttu-id="db91c-111">attribute</span><span class="sxs-lookup"><span data-stu-id="db91c-111">Attribute</span></span>|<span data-ttu-id="db91c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="db91c-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="db91c-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="db91c-113">Required attribute.</span></span> <span data-ttu-id="db91c-114">Упогоняет имя типа, включая пространство имен, которое служит в качестве менеджера домена приложения для домена приложения по умолчанию в процессе.</span><span class="sxs-lookup"><span data-stu-id="db91c-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db91c-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="db91c-115">Child Elements</span></span>  
 <span data-ttu-id="db91c-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="db91c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db91c-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="db91c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="db91c-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="db91c-118">Element</span></span>|<span data-ttu-id="db91c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="db91c-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="db91c-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db91c-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="db91c-121">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="db91c-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db91c-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="db91c-122">Remarks</span></span>  
 <span data-ttu-id="db91c-123">Чтобы указать тип менеджера домена приложения, необходимо указать как этот элемент, так и [ \<элемент appDomainManagerAssembly>](appdomainmanagerassembly-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="db91c-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="db91c-124">Если какой-либо из этих элементов не указан, другой игнорируется.</span><span class="sxs-lookup"><span data-stu-id="db91c-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="db91c-125">При загрузке <xref:System.TypeLoadException> домена приложения по умолчанию, если указанный тип не существует в сборке, указанной [ \<элементом appDomainManagerAssembly>;](appdomainmanagerassembly-element.md) и процесс не может начаться.</span><span class="sxs-lookup"><span data-stu-id="db91c-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="db91c-126">При указании типа менеджера домена приложения для домена приложения по умолчанию другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип менеджера домена приложения.</span><span class="sxs-lookup"><span data-stu-id="db91c-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="db91c-127">Используйте <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> и свойства, чтобы указать другой тип менеджера домена приложения для нового домена приложения.</span><span class="sxs-lookup"><span data-stu-id="db91c-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="db91c-128">Определение типа диспетчера домена приложения требует, чтобы приложение было полностью доверчиво.</span><span class="sxs-lookup"><span data-stu-id="db91c-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="db91c-129">(Например, приложение, работая на рабочем столе, имеет полное доверие.) Если приложение не имеет полного <xref:System.TypeLoadException> доверия, a брошен.</span><span class="sxs-lookup"><span data-stu-id="db91c-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="db91c-130">Формат типа и пространства имен является тем же форматом, который используется для <xref:System.Type.FullName%2A?displayProperty=nameWithType> свойства.</span><span class="sxs-lookup"><span data-stu-id="db91c-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="db91c-131">Этот элемент конфигурации доступен только в системе .NET 4 и позже.</span><span class="sxs-lookup"><span data-stu-id="db91c-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db91c-132">Пример</span><span class="sxs-lookup"><span data-stu-id="db91c-132">Example</span></span>  
 <span data-ttu-id="db91c-133">В следующем примере показано, как указать, что менеджер домена `MyMgr` приложения `AdMgrExample` для домена приложения приложения по умолчанию процесса — это тип сборки.</span><span class="sxs-lookup"><span data-stu-id="db91c-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="db91c-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="db91c-134">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="db91c-135">\<appDomainManagerСборка> Элемент</span><span class="sxs-lookup"><span data-stu-id="db91c-135">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="db91c-136">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="db91c-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="db91c-137">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="db91c-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="db91c-138">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="db91c-138">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
