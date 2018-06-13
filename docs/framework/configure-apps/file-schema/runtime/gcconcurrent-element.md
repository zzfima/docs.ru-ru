---
title: '&lt;gcConcurrent&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee00c3a307523d2cae831274630ad6828cd9daf6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745842"
---
# <a name="ltgcconcurrentgt-element"></a><span data-ttu-id="9e470-102">&lt;gcConcurrent&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="9e470-102">&lt;gcConcurrent&gt; Element</span></span>
<span data-ttu-id="9e470-103">Указывает, выполняет ли среда CLR сборку мусора в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="9e470-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>  
  
 <span data-ttu-id="9e470-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9e470-104">\<configuration></span></span>  
<span data-ttu-id="9e470-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="9e470-105">\<runtime></span></span>  
<span data-ttu-id="9e470-106">\<gcConcurrent ></span><span class="sxs-lookup"><span data-stu-id="9e470-106">\<gcConcurrent></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e470-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e470-107">Syntax</span></span>  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e470-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9e470-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9e470-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9e470-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e470-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9e470-110">Attributes</span></span>  
  
|<span data-ttu-id="9e470-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9e470-111">Attribute</span></span>|<span data-ttu-id="9e470-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9e470-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9e470-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9e470-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9e470-114">Указывает, выполняет ли среда выполнения сборку мусора параллельно.</span><span class="sxs-lookup"><span data-stu-id="9e470-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9e470-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="9e470-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9e470-116">Значение</span><span class="sxs-lookup"><span data-stu-id="9e470-116">Value</span></span>|<span data-ttu-id="9e470-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9e470-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9e470-118">Сборка мусора не выполняется параллельно.</span><span class="sxs-lookup"><span data-stu-id="9e470-118">Does not run garbage collection concurrently.</span></span>|  
|`true`|<span data-ttu-id="9e470-119">Сборка мусора выполняется параллельно.</span><span class="sxs-lookup"><span data-stu-id="9e470-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="9e470-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9e470-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e470-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9e470-121">Child Elements</span></span>  
 <span data-ttu-id="9e470-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9e470-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e470-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9e470-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9e470-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="9e470-124">Element</span></span>|<span data-ttu-id="9e470-125">Описание</span><span class="sxs-lookup"><span data-stu-id="9e470-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9e470-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9e470-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9e470-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="9e470-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e470-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e470-128">Remarks</span></span>  
 <span data-ttu-id="9e470-129">До .NET Framework 4 сборка мусора рабочей станции поддерживала параллельную сборку мусора, которая выполнялась в фоновом режиме в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="9e470-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="9e470-130">В .NET Framework 4 параллельная сборка мусора была заменена фоновой сборкой мусора, которая также выполняется в фоновом режиме в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="9e470-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="9e470-131">Начиная с .NET Framework 4.5 фоновая сборка мусора стала доступна для сборки мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="9e470-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="9e470-132">Элемент `<gcConcurrent>` управляет тем, какую сборку мусора выполняет среда выполнения —параллельную или фоновую сборку мусора, если она доступна, либо сборку мусора на переднем плане.</span><span class="sxs-lookup"><span data-stu-id="9e470-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it is available, or whether it performs garbage collection in the foreground.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="9e470-133">Начиная с .NET Framework 4, параллельная сборка мусора заменена на фоновую сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="9e470-133">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="9e470-134">Условия *параллельных* и *фона* взаимозаменяемы в документации по платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9e470-134">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="9e470-135">Чтобы отключить фоновую сборку мусора, используйте элемент `<gcConcurrent>`, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9e470-135">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>  
  
 <span data-ttu-id="9e470-136">По умолчанию среда выполнения использует параллельную или фоновую сборку мусора, которая оптимизирована по задержкам.</span><span class="sxs-lookup"><span data-stu-id="9e470-136">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="9e470-137">Если приложение подразумевает активное взаимодействие с пользователем, рекомендуется использовать параллельную сборку мусора, чтобы сократить паузы в работе приложения, возникающие при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="9e470-137">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="9e470-138">Если атрибут `enabled` элемента `<gcConcurrent>` имеет значение `false`, среда выполнения использует непараллельную сборку мусора, которая оптимизирована по производительности.</span><span class="sxs-lookup"><span data-stu-id="9e470-138">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="9e470-139">В следующем файле конфигурации отключается фоновая сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="9e470-139">The following configuration file disables background garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="9e470-140">Если в файле конфигурации компьютера имеется параметр `<gcConcurrentSetting>`, он определяет значение по умолчанию для всех приложений .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9e470-140">If there is a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="9e470-141">Параметр в файле конфигурации компьютера переопределяет параметр в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="9e470-141">The machine configuration file setting overrides the application configuration file setting.</span></span>  
  
 <span data-ttu-id="9e470-142">Дополнительные сведения о параллельной и фоновой сборке мусора см. в разделе «параллельная сборка мусора» [основы сборки мусора](../../../../../docs/standard/garbage-collection/fundamentals.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="9e470-142">For more information on concurrent and background garbage collection, see the "Concurrent garbage collection" section in the [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e470-143">Пример</span><span class="sxs-lookup"><span data-stu-id="9e470-143">Example</span></span>  
 <span data-ttu-id="9e470-144">В следующем примере включается параллельная сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="9e470-144">The following example enables concurrent garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e470-145">См. также</span><span class="sxs-lookup"><span data-stu-id="9e470-145">See Also</span></span>  
 [<span data-ttu-id="9e470-146">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="9e470-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="9e470-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="9e470-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="9e470-148">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="9e470-148">Fundamentals of Garbage Collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md)
