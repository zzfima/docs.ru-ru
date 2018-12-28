---
title: '&lt;Проверка&gt; элемент'
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
ms.openlocfilehash: a5b9be3050da21c0a99931ca70cf990b0b8bf1fe
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612313"
---
# <a name="ltprobinggt-element"></a><span data-ttu-id="1d72e-102">&lt;Проверка&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="1d72e-102">&lt;probing&gt; Element</span></span>
<span data-ttu-id="1d72e-103">Задает базовые вложенные папки приложения для поиска при загрузке сборки среда CLR.</span><span class="sxs-lookup"><span data-stu-id="1d72e-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
 <span data-ttu-id="1d72e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1d72e-104">\<configuration></span></span>  
<span data-ttu-id="1d72e-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="1d72e-105">\<runtime></span></span>  
<span data-ttu-id="1d72e-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="1d72e-106">\<assemblyBinding></span></span>  
<span data-ttu-id="1d72e-107">\<probing ></span><span class="sxs-lookup"><span data-stu-id="1d72e-107">\<probing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d72e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d72e-108">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d72e-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1d72e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1d72e-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1d72e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d72e-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1d72e-111">Attributes</span></span>  
  
|<span data-ttu-id="1d72e-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1d72e-112">Attribute</span></span>|<span data-ttu-id="1d72e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1d72e-113">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="1d72e-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="1d72e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="1d72e-115">Задает вложенные папки базовой папки приложения, которые могут содержать сборки.</span><span class="sxs-lookup"><span data-stu-id="1d72e-115">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="1d72e-116">Каждая вложенная папка точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="1d72e-116">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d72e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1d72e-117">Child Elements</span></span>  
 <span data-ttu-id="1d72e-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1d72e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d72e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1d72e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1d72e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="1d72e-120">Element</span></span>|<span data-ttu-id="1d72e-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="1d72e-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="1d72e-122">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="1d72e-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="1d72e-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1d72e-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1d72e-124">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="1d72e-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1d72e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="1d72e-125">Example</span></span>  
 <span data-ttu-id="1d72e-126">Приведенный ниже показано, как указать базовых вложенных папок приложения, в которых среда выполнения должна искать сборки.</span><span class="sxs-lookup"><span data-stu-id="1d72e-126">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d72e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1d72e-127">See Also</span></span>  
- [<span data-ttu-id="1d72e-128">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="1d72e-128">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="1d72e-129">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="1d72e-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="1d72e-130">Указание расположения сборки</span><span class="sxs-lookup"><span data-stu-id="1d72e-130">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
- [<span data-ttu-id="1d72e-131">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="1d72e-131">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
