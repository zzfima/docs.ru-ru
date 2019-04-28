---
title: Элемент <gcConcurrent>
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
ms.openlocfilehash: 0e2be4d9384f1e1ef73ce6064184aa2621a517a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674107"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="bc712-102">\<gcConcurrent > элемент</span><span class="sxs-lookup"><span data-stu-id="bc712-102">\<gcConcurrent> Element</span></span>

<span data-ttu-id="bc712-103">Указывает, выполняет ли среда CLR сборку мусора в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="bc712-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="bc712-104">\<Конфигурация > \\</span><span class="sxs-lookup"><span data-stu-id="bc712-104">\<configuration>\\</span></span>
<span data-ttu-id="bc712-105">\<Среда выполнения > \\</span><span class="sxs-lookup"><span data-stu-id="bc712-105">\<runtime>\\</span></span>
<span data-ttu-id="bc712-106">\<gcConcurrent></span><span class="sxs-lookup"><span data-stu-id="bc712-106">\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="bc712-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc712-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bc712-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="bc712-108">Attributes and elements</span></span>

<span data-ttu-id="bc712-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bc712-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bc712-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bc712-110">Attributes</span></span>

|<span data-ttu-id="bc712-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bc712-111">Attribute</span></span>|<span data-ttu-id="bc712-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bc712-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="bc712-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bc712-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="bc712-114">Указывает, выполняет ли среда выполнения сборку мусора параллельно.</span><span class="sxs-lookup"><span data-stu-id="bc712-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="bc712-115">атрибут Enabled</span><span class="sxs-lookup"><span data-stu-id="bc712-115">enabled attribute</span></span>

|<span data-ttu-id="bc712-116">Значение</span><span class="sxs-lookup"><span data-stu-id="bc712-116">Value</span></span>|<span data-ttu-id="bc712-117">Описание</span><span class="sxs-lookup"><span data-stu-id="bc712-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="bc712-118">Не выполнять сборку мусора параллельно.</span><span class="sxs-lookup"><span data-stu-id="bc712-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="bc712-119">Сборка мусора выполняется параллельно.</span><span class="sxs-lookup"><span data-stu-id="bc712-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="bc712-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bc712-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="bc712-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bc712-121">Child elements</span></span>

<span data-ttu-id="bc712-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bc712-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bc712-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bc712-123">Parent elements</span></span>

|<span data-ttu-id="bc712-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="bc712-124">Element</span></span>|<span data-ttu-id="bc712-125">Описание</span><span class="sxs-lookup"><span data-stu-id="bc712-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="bc712-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc712-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="bc712-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="bc712-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bc712-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc712-128">Remarks</span></span>

<span data-ttu-id="bc712-129">До .NET Framework 4 сборка мусора рабочей станции поддерживала параллельную сборку мусора, которая выполнялась в фоновом режиме в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="bc712-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="bc712-130">В .NET Framework 4 параллельная сборка мусора была заменена фоновой сборкой мусора, которая также выполняется в фоновом режиме в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="bc712-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="bc712-131">Начиная с .NET Framework 4.5 фоновая сборка мусора стала доступна для сборки мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="bc712-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="bc712-132">`<gcConcurrent>` Элемент управляет, выполняет ли среда выполнения параллельную или фоновую сборку мусора, если таковой имеется, или он выполняет сборку мусора на переднем плане.</span><span class="sxs-lookup"><span data-stu-id="bc712-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="bc712-133">Чтобы отключить фоновую сборку мусора</span><span class="sxs-lookup"><span data-stu-id="bc712-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="bc712-134">Начиная с .NET Framework 4, параллельная сборка мусора заменена на фоновую сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="bc712-134">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="bc712-135">Условия *параллельных* и *фона* являются взаимозаменяемыми в документации по .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc712-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="bc712-136">Чтобы отключить фоновую сборку мусора, используйте элемент `<gcConcurrent>`, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bc712-136">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>

<span data-ttu-id="bc712-137">По умолчанию среда выполнения использует параллельную или фоновую сборку мусора, которая оптимизирована по задержкам.</span><span class="sxs-lookup"><span data-stu-id="bc712-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="bc712-138">Если приложение подразумевает активное взаимодействие с пользователем, рекомендуется использовать параллельную сборку мусора, чтобы сократить паузы в работе приложения, возникающие при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="bc712-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="bc712-139">Если атрибут `enabled` элемента `<gcConcurrent>` имеет значение `false`, среда выполнения использует непараллельную сборку мусора, которая оптимизирована по производительности.</span><span class="sxs-lookup"><span data-stu-id="bc712-139">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="bc712-140">В следующем файле конфигурации отключается фоновая сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="bc712-140">The following configuration file disables background garbage collection.</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 <span data-ttu-id="bc712-141">Если имеется `<gcConcurrentSetting>` параметр в файле конфигурации компьютера, он определяет значение по умолчанию для всех приложений .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc712-141">If there's a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="bc712-142">Параметр в файле конфигурации компьютера переопределяет параметр в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="bc712-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

 <span data-ttu-id="bc712-143">Дополнительные сведения о параллельной и фоновой сборки мусора, см. в разделе [параллельная сборка мусора](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) статьи [основы сборки мусора](../../../../standard/garbage-collection/fundamentals.md) статьи.</span><span class="sxs-lookup"><span data-stu-id="bc712-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) section in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="bc712-144">Пример</span><span class="sxs-lookup"><span data-stu-id="bc712-144">Example</span></span>

<span data-ttu-id="bc712-145">В следующем примере включается параллельная сборка мусора:</span><span class="sxs-lookup"><span data-stu-id="bc712-145">The following example enables concurrent garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="bc712-146">См. также</span><span class="sxs-lookup"><span data-stu-id="bc712-146">See also</span></span>

- [<span data-ttu-id="bc712-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="bc712-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bc712-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="bc712-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bc712-149">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="bc712-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
