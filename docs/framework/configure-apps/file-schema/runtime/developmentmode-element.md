---
title: Элемент <developmentMode>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
ms.openlocfilehash: 4a062da31740edb8f0c7a4f4db8b09800c687587
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117631"
---
# <a name="developmentmode-element"></a><span data-ttu-id="8a997-102">\<developmentMode > элемент</span><span class="sxs-lookup"><span data-stu-id="8a997-102">\<developmentMode> Element</span></span>
<span data-ttu-id="8a997-103">Указывает, выполняет ли среда поиск сборок в каталогах, указанных в переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="8a997-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
<span data-ttu-id="8a997-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8a997-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8a997-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="8a997-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="8a997-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<developmentMode >**</span><span class="sxs-lookup"><span data-stu-id="8a997-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a997-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a997-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a997-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8a997-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8a997-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8a997-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a997-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8a997-110">Attributes</span></span>  
  
|<span data-ttu-id="8a997-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8a997-111">Attribute</span></span>|<span data-ttu-id="8a997-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8a997-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a997-113">**девелоперинсталлатион**</span><span class="sxs-lookup"><span data-stu-id="8a997-113">**developerInstallation**</span></span>|<span data-ttu-id="8a997-114">Указывает, выполняет ли среда поиск сборок в каталогах, указанных в переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="8a997-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="8a997-115">Атрибут Девелоперинсталлатион</span><span class="sxs-lookup"><span data-stu-id="8a997-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="8a997-116">значения</span><span class="sxs-lookup"><span data-stu-id="8a997-116">Value</span></span>|<span data-ttu-id="8a997-117">Описание</span><span class="sxs-lookup"><span data-stu-id="8a997-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a997-118">**true**</span><span class="sxs-lookup"><span data-stu-id="8a997-118">**true**</span></span>|<span data-ttu-id="8a997-119">Выполняет поиск сборок в каталогах, заданных переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="8a997-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="8a997-120">**false**</span><span class="sxs-lookup"><span data-stu-id="8a997-120">**false**</span></span>|<span data-ttu-id="8a997-121">Не выполняет поиск сборок в каталогах, заданных переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="8a997-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="8a997-122">Это значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8a997-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a997-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8a997-123">Child Elements</span></span>  
 <span data-ttu-id="8a997-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8a997-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a997-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8a997-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8a997-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a997-126">Element</span></span>|<span data-ttu-id="8a997-127">Описание</span><span class="sxs-lookup"><span data-stu-id="8a997-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8a997-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8a997-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8a997-129">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="8a997-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a997-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="8a997-130">Remarks</span></span>  
 <span data-ttu-id="8a997-131">Используйте этот параметр только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="8a997-131">Use this setting only at development time.</span></span> <span data-ttu-id="8a997-132">Среда выполнения не проверяет версии сборок со строгими именами, найденных в DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="8a997-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="8a997-133">Он просто использует первую найденную сборку.</span><span class="sxs-lookup"><span data-stu-id="8a997-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a997-134">Пример</span><span class="sxs-lookup"><span data-stu-id="8a997-134">Example</span></span>  
 <span data-ttu-id="8a997-135">В следующем примере показано, как заставить среду выполнения искать сборки в каталогах, заданных переменной среды DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="8a997-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a997-136">См. также</span><span class="sxs-lookup"><span data-stu-id="8a997-136">See also</span></span>

- [<span data-ttu-id="8a997-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="8a997-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8a997-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="8a997-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="8a997-139">Практическое руководство. Поиск сборок с помощью DEVPATH</span><span class="sxs-lookup"><span data-stu-id="8a997-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
