---
title: Элемент <qualifyAssembly>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153923"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="c4c44-102">\<квалификацияСборка> Элемент</span><span class="sxs-lookup"><span data-stu-id="c4c44-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="c4c44-103">Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.</span><span class="sxs-lookup"><span data-stu-id="c4c44-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="c4c44-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4c44-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c4c44-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4c44-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="c4c44-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<сборкаОбязательная>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="c4c44-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="c4c44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<квалификацияСобрание>**</span><span class="sxs-lookup"><span data-stu-id="c4c44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c44-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4c44-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4c44-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c4c44-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c4c44-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c4c44-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4c44-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c4c44-111">Attributes</span></span>  
  
|<span data-ttu-id="c4c44-112">attribute</span><span class="sxs-lookup"><span data-stu-id="c4c44-112">Attribute</span></span>|<span data-ttu-id="c4c44-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c4c44-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="c4c44-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c4c44-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="c4c44-115">Определяет частичное название сборки по мере ее отослания в коде.</span><span class="sxs-lookup"><span data-stu-id="c4c44-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="c4c44-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c4c44-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c4c44-117">Упоняет полное название сборки, как она появляется в глобальном кэше сборки.</span><span class="sxs-lookup"><span data-stu-id="c4c44-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4c44-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c4c44-118">Child Elements</span></span>  
 <span data-ttu-id="c4c44-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="c4c44-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4c44-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c4c44-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c4c44-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="c4c44-121">Element</span></span>|<span data-ttu-id="c4c44-122">Описание</span><span class="sxs-lookup"><span data-stu-id="c4c44-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="c4c44-123">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="c4c44-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="c4c44-124">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c4c44-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c4c44-125">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="c4c44-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4c44-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4c44-126">Remarks</span></span>  
 <span data-ttu-id="c4c44-127">Вызов <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> метода с использованием названий частичной сборки приводит к тому, что время выполнения общего языка будет искать сборку только в базовом каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="c4c44-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="c4c44-128">Используйте \*\* \<элемент квалификационной сборки>\*\* в файле конфигурации приложения, чтобы предоставить полную информацию о сборке (имя, версия, маркер общедоступного ключа и культуру) и вызвать время выполнения общего языка для поиска сборки в глобальном кэше сборки.</span><span class="sxs-lookup"><span data-stu-id="c4c44-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="c4c44-129">Атрибут **fullName** должен включать четыре поля идентификатора сборки: имя, версия, маркер общедоступных ключей и культуру.</span><span class="sxs-lookup"><span data-stu-id="c4c44-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="c4c44-130">Атрибут **частичного имени** должен частично ссылаться на сборку.</span><span class="sxs-lookup"><span data-stu-id="c4c44-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="c4c44-131">Необходимо указать хотя бы имя текста сборки (наиболее распространенный случай), но вы также можете включить версию, маркер общедоступного ключа или культуру (или любую комбинацию из четырех, но не все четыре).</span><span class="sxs-lookup"><span data-stu-id="c4c44-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="c4c44-132">**PartialName** должен соответствовать имени, указанному в вашем вызове.</span><span class="sxs-lookup"><span data-stu-id="c4c44-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="c4c44-133">Например, нельзя `"math"` указать атрибут **частичного имени** `Assembly.Load("math, Version=3.3.3.3")` в файле конфигурации и вызов в коде.</span><span class="sxs-lookup"><span data-stu-id="c4c44-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4c44-134">Пример</span><span class="sxs-lookup"><span data-stu-id="c4c44-134">Example</span></span>  
 <span data-ttu-id="c4c44-135">Следующий пример логически превращает `Assembly.Load("math")` `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`вызов в .</span><span class="sxs-lookup"><span data-stu-id="c4c44-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4c44-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c4c44-136">See also</span></span>

- [<span data-ttu-id="c4c44-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="c4c44-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c4c44-138">Как Время выполнения находит сборки</span><span class="sxs-lookup"><span data-stu-id="c4c44-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="c4c44-139">[Частичные ссылки на сборки](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c4c44-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
