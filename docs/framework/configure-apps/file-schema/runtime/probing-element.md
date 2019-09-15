---
title: Элемент <probing>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae789e99a1306102c67f2252760e215989132406
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971630"
---
# <a name="probing-element"></a><span data-ttu-id="76d00-102">\<Элемент > проверки</span><span class="sxs-lookup"><span data-stu-id="76d00-102">\<probing> Element</span></span>
<span data-ttu-id="76d00-103">Задает базовые подкаталоги приложения для поиска средой CLR при загрузке сборок.</span><span class="sxs-lookup"><span data-stu-id="76d00-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
<span data-ttu-id="76d00-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="76d00-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="76d00-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="76d00-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="76d00-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="76d00-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="76d00-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Проверка >**</span><span class="sxs-lookup"><span data-stu-id="76d00-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76d00-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76d00-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76d00-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="76d00-109">Attributes and Elements</span></span>  
 <span data-ttu-id="76d00-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="76d00-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76d00-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="76d00-111">Attributes</span></span>  
  
|<span data-ttu-id="76d00-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="76d00-112">Attribute</span></span>|<span data-ttu-id="76d00-113">Описание</span><span class="sxs-lookup"><span data-stu-id="76d00-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="76d00-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="76d00-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="76d00-115">Указывает подкаталоги базового каталога приложения, которые могут содержать сборки.</span><span class="sxs-lookup"><span data-stu-id="76d00-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="76d00-116">Для каждого подкаталога следует выделить точку с запятой.</span><span class="sxs-lookup"><span data-stu-id="76d00-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76d00-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="76d00-117">Child Elements</span></span>  

<span data-ttu-id="76d00-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="76d00-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76d00-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="76d00-119">Parent Elements</span></span>  
  
|<span data-ttu-id="76d00-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="76d00-120">Element</span></span>|<span data-ttu-id="76d00-121">Описание</span><span class="sxs-lookup"><span data-stu-id="76d00-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="76d00-122">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="76d00-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="76d00-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="76d00-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="76d00-124">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="76d00-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="76d00-125">Пример</span><span class="sxs-lookup"><span data-stu-id="76d00-125">Example</span></span>  
 <span data-ttu-id="76d00-126">В следующем примере показано, как задать базовые подкаталоги приложения, которые среда выполнения должна использовать для поиска сборок.</span><span class="sxs-lookup"><span data-stu-id="76d00-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="76d00-127">См. также</span><span class="sxs-lookup"><span data-stu-id="76d00-127">See also</span></span>

- [<span data-ttu-id="76d00-128">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="76d00-128">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="76d00-129">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="76d00-129">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="76d00-130">Укажите расположение сборки</span><span class="sxs-lookup"><span data-stu-id="76d00-130">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="76d00-131">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="76d00-131">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
