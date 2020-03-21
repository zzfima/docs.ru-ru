---
title: Элемент <dependentAssembly>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
ms.openlocfilehash: 2de8c752867d00708173d11d1851f415a2e8518d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154209"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="f091c-102">\<зависимаясборка> Элемент</span><span class="sxs-lookup"><span data-stu-id="f091c-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="f091c-103">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="f091c-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="f091c-104">Используйте `dependentAssembly` один элемент для каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="f091c-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
<span data-ttu-id="f091c-105">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f091c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f091c-106">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="f091c-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f091c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<сборкаОбязательная>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="f091c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="f091c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<зависимаясборка>**</span><span class="sxs-lookup"><span data-stu-id="f091c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f091c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f091c-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f091c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f091c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f091c-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f091c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f091c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f091c-112">Attributes</span></span>  
 <span data-ttu-id="f091c-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="f091c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f091c-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f091c-114">Child Elements</span></span>  
  
|<span data-ttu-id="f091c-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="f091c-115">Element</span></span>|<span data-ttu-id="f091c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f091c-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="f091c-117">Содержит идентифицирующую информацию о сборке.</span><span class="sxs-lookup"><span data-stu-id="f091c-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="f091c-118">Этот элемент должен быть `dependentAssembly` включен в каждый элемент.</span><span class="sxs-lookup"><span data-stu-id="f091c-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="f091c-119">Указывается, где время выполнения может найти общую сборку, если она не установлена на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f091c-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="f091c-120">Перенаправляет одну версию сборки на другую.</span><span class="sxs-lookup"><span data-stu-id="f091c-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="f091c-121">Определяет, применяется ли политика издателя для этой сборки.</span><span class="sxs-lookup"><span data-stu-id="f091c-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f091c-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f091c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f091c-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="f091c-123">Element</span></span>|<span data-ttu-id="f091c-124">Описание</span><span class="sxs-lookup"><span data-stu-id="f091c-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="f091c-125">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="f091c-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="f091c-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f091c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f091c-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="f091c-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f091c-128">Пример</span><span class="sxs-lookup"><span data-stu-id="f091c-128">Example</span></span>  
 <span data-ttu-id="f091c-129">В следующем примере показано, как инкапсулировать информацию о сборке для двух сборок.</span><span class="sxs-lookup"><span data-stu-id="f091c-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f091c-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f091c-130">See also</span></span>

- [<span data-ttu-id="f091c-131">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f091c-131">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f091c-132">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="f091c-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f091c-133">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="f091c-133">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
