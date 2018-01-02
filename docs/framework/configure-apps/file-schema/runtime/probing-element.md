---
title: "&lt;Проверка&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e846cb1386dc64161d91ab50b6a04e5560e9c6da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltprobinggt-element"></a><span data-ttu-id="24dc7-102">&lt;Проверка&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="24dc7-102">&lt;probing&gt; Element</span></span>
<span data-ttu-id="24dc7-103">Задает базовые вложенные папки приложения для поиска при загрузке сборки среда.</span><span class="sxs-lookup"><span data-stu-id="24dc7-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
 <span data-ttu-id="24dc7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="24dc7-104">\<configuration></span></span>  
<span data-ttu-id="24dc7-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="24dc7-105">\<runtime></span></span>  
<span data-ttu-id="24dc7-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="24dc7-106">\<assemblyBinding></span></span>  
<span data-ttu-id="24dc7-107">\<Проверка ></span><span class="sxs-lookup"><span data-stu-id="24dc7-107">\<probing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24dc7-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24dc7-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24dc7-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="24dc7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="24dc7-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="24dc7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24dc7-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="24dc7-111">Attributes</span></span>  
  
|<span data-ttu-id="24dc7-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="24dc7-112">Attribute</span></span>|<span data-ttu-id="24dc7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="24dc7-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="24dc7-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="24dc7-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="24dc7-115">Задает вложенные папки базовой папке приложения, которые могут содержать сборки.</span><span class="sxs-lookup"><span data-stu-id="24dc7-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="24dc7-116">Каждая вложенная папка точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="24dc7-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24dc7-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="24dc7-117">Child Elements</span></span>  
 <span data-ttu-id="24dc7-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="24dc7-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24dc7-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="24dc7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="24dc7-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="24dc7-120">Element</span></span>|<span data-ttu-id="24dc7-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="24dc7-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="24dc7-122">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="24dc7-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="24dc7-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="24dc7-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="24dc7-124">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="24dc7-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="24dc7-125">Пример</span><span class="sxs-lookup"><span data-stu-id="24dc7-125">Example</span></span>  
 <span data-ttu-id="24dc7-126">Приведенный ниже показано, как указать базовых вложенных папок приложения, в которых среда выполнения должна искать сборки.</span><span class="sxs-lookup"><span data-stu-id="24dc7-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="24dc7-127">См. также</span><span class="sxs-lookup"><span data-stu-id="24dc7-127">See Also</span></span>  
 [<span data-ttu-id="24dc7-128">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="24dc7-128">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="24dc7-129">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="24dc7-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="24dc7-130">Указание расположения сборки</span><span class="sxs-lookup"><span data-stu-id="24dc7-130">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [<span data-ttu-id="24dc7-131">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="24dc7-131">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
