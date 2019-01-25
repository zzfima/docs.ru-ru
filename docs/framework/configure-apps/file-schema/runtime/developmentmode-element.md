---
title: '&lt;developmentMode&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f6a48a055d98a2f0b379df612da4e8fd49f3987
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669098"
---
# <a name="ltdevelopmentmodegt-element"></a><span data-ttu-id="86f3d-102">&lt;developmentMode&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="86f3d-102">&lt;developmentMode&gt; Element</span></span>
<span data-ttu-id="86f3d-103">Указывает, выполняет ли среда поиск сборок в каталогах, указанных в переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="86f3d-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
 <span data-ttu-id="86f3d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="86f3d-104">\<configuration></span></span>  
<span data-ttu-id="86f3d-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="86f3d-105">\<runtime></span></span>  
<span data-ttu-id="86f3d-106">\<developmentMode ></span><span class="sxs-lookup"><span data-stu-id="86f3d-106">\<developmentMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86f3d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86f3d-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86f3d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="86f3d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="86f3d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="86f3d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86f3d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="86f3d-110">Attributes</span></span>  
  
|<span data-ttu-id="86f3d-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="86f3d-111">Attribute</span></span>|<span data-ttu-id="86f3d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="86f3d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86f3d-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="86f3d-113">**developerInstallation**</span></span>|<span data-ttu-id="86f3d-114">Указывает, выполняет ли среда поиск сборок в каталогах, указанных в переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="86f3d-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="86f3d-115">developerInstallation атрибут</span><span class="sxs-lookup"><span data-stu-id="86f3d-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="86f3d-116">Значение</span><span class="sxs-lookup"><span data-stu-id="86f3d-116">Value</span></span>|<span data-ttu-id="86f3d-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="86f3d-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="86f3d-118">**true**</span><span class="sxs-lookup"><span data-stu-id="86f3d-118">**true**</span></span>|<span data-ttu-id="86f3d-119">Поиск сборок в каталогах, указанных в переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="86f3d-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="86f3d-120">**false**</span><span class="sxs-lookup"><span data-stu-id="86f3d-120">**false**</span></span>|<span data-ttu-id="86f3d-121">Не выполняет поиск сборок в каталогах, указанных в переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="86f3d-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="86f3d-122">Это значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="86f3d-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86f3d-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="86f3d-123">Child Elements</span></span>  
 <span data-ttu-id="86f3d-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="86f3d-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86f3d-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="86f3d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="86f3d-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="86f3d-126">Element</span></span>|<span data-ttu-id="86f3d-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="86f3d-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="86f3d-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="86f3d-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="86f3d-129">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="86f3d-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86f3d-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="86f3d-130">Remarks</span></span>  
 <span data-ttu-id="86f3d-131">Используйте этот параметр только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="86f3d-131">Use this setting only at development time.</span></span> <span data-ttu-id="86f3d-132">Среда выполнения не проверяет версии на в DEVPATH сборок со строгим именем.</span><span class="sxs-lookup"><span data-stu-id="86f3d-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="86f3d-133">Он просто использует первый найденную сборку.</span><span class="sxs-lookup"><span data-stu-id="86f3d-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86f3d-134">Пример</span><span class="sxs-lookup"><span data-stu-id="86f3d-134">Example</span></span>  
 <span data-ttu-id="86f3d-135">В следующем примере показано, как среда выполнения для поиска сборок в каталогах, указанных в переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="86f3d-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="86f3d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="86f3d-136">See also</span></span>
- [<span data-ttu-id="86f3d-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="86f3d-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="86f3d-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="86f3d-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="86f3d-139">Практическое руководство. Поиск сборок с помощью DEVPATH</span><span class="sxs-lookup"><span data-stu-id="86f3d-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
