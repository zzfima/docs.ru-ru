---
title: Элемент <gcServer>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa03179df1cd2595b4be428106dd3ec10b309317
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252553"
---
# <a name="gcserver-element"></a><span data-ttu-id="84d03-102">\<Элемент > gcServer</span><span class="sxs-lookup"><span data-stu-id="84d03-102">\<gcServer> Element</span></span>
<span data-ttu-id="84d03-103">Указывает, выполняет ли среда CLR сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="84d03-103">Specifies whether the common language runtime runs server garbage collection.</span></span>  
  
<span data-ttu-id="84d03-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="84d03-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="84d03-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="84d03-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="84d03-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gcServer >**</span><span class="sxs-lookup"><span data-stu-id="84d03-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcServer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84d03-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84d03-107">Syntax</span></span>  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84d03-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="84d03-108">Attributes and Elements</span></span>  
 <span data-ttu-id="84d03-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="84d03-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84d03-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="84d03-110">Attributes</span></span>  
  
|<span data-ttu-id="84d03-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="84d03-111">Attribute</span></span>|<span data-ttu-id="84d03-112">Описание</span><span class="sxs-lookup"><span data-stu-id="84d03-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="84d03-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="84d03-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="84d03-114">Указывает, выполняет ли среда выполнения сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="84d03-114">Specifies whether the runtime runs server garbage collection.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="84d03-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="84d03-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="84d03-116">Значение</span><span class="sxs-lookup"><span data-stu-id="84d03-116">Value</span></span>|<span data-ttu-id="84d03-117">Описание</span><span class="sxs-lookup"><span data-stu-id="84d03-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="84d03-118">Не выполняет сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="84d03-118">Does not run server garbage collection.</span></span> <span data-ttu-id="84d03-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="84d03-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="84d03-120">Выполняет сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="84d03-120">Runs server garbage collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84d03-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="84d03-121">Child Elements</span></span>  
 <span data-ttu-id="84d03-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="84d03-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84d03-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="84d03-123">Parent Elements</span></span>  
  
|<span data-ttu-id="84d03-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="84d03-124">Element</span></span>|<span data-ttu-id="84d03-125">Описание</span><span class="sxs-lookup"><span data-stu-id="84d03-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="84d03-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="84d03-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="84d03-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="84d03-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84d03-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="84d03-128">Remarks</span></span>  
 <span data-ttu-id="84d03-129">Среда CLR поддерживает два типа сборки мусора: сборку мусора рабочей станции, которая доступна во всех системах, и сборку мусора сервера, которая доступна в многопроцессорных системах.</span><span class="sxs-lookup"><span data-stu-id="84d03-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="84d03-130">Для управления типом сборки мусора среды CLR можно использовать элемент `<gcServer>`.</span><span class="sxs-lookup"><span data-stu-id="84d03-130">You use the `<gcServer>` element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="84d03-131">Используйте свойство <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>, чтобы определить, включена ли сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="84d03-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>  
  
 <span data-ttu-id="84d03-132">Для однопроцессорных компьютеров сборка мусора рабочей станции по умолчанию должна быть самым быстрым вариантом.</span><span class="sxs-lookup"><span data-stu-id="84d03-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="84d03-133">Для двухпроцессорных компьютеров можно использовать сборку мусора как рабочей станции, так и сервера.</span><span class="sxs-lookup"><span data-stu-id="84d03-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="84d03-134">Сборка мусора сервера должно быть самым быстрым вариантом при наличии более двух процессоров.</span><span class="sxs-lookup"><span data-stu-id="84d03-134">Server garbage collection should be the fastest option for more than two processors.</span></span>  
  
 <span data-ttu-id="84d03-135">Этот элемент может использоваться только в файле конфигурации приложения; в файле конфигурации компьютера он игнорируется.</span><span class="sxs-lookup"><span data-stu-id="84d03-135">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84d03-136">В платформе .NET Framework версии 4 и более ранних версиях параллельная сборка мусора недоступна, если включена серверная сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="84d03-136">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="84d03-137">С версии .NET Framework 4.5 серверная сборка мусора является параллельной.</span><span class="sxs-lookup"><span data-stu-id="84d03-137">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="84d03-138">Чтобы использовать непараллельную сборку мусора сервера, `<gcServer>` установите для `true` элемента значение, а `false` [ \<для элемента gcConcurrent >](gcconcurrent-element.md) значение.</span><span class="sxs-lookup"><span data-stu-id="84d03-138">To use non-concurrent server garbage collection, set the `<gcServer>` element to `true` and the [\<gcConcurrent> element](gcconcurrent-element.md) to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84d03-139">Пример</span><span class="sxs-lookup"><span data-stu-id="84d03-139">Example</span></span>  
 <span data-ttu-id="84d03-140">В следующем примере включается параллельная сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="84d03-140">The following example enables server garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="84d03-141">См. также</span><span class="sxs-lookup"><span data-stu-id="84d03-141">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="84d03-142">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="84d03-142">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="84d03-143">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="84d03-143">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="84d03-144">Отключение параллельной сборки мусора</span><span class="sxs-lookup"><span data-stu-id="84d03-144">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
