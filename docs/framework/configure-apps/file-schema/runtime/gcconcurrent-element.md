---
title: gcConcurrent Элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 5957337aa960a0d5f445249b410dbfaddb7b08e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400983"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="5cdf0-102">\<gcConcurrent> элемент</span><span class="sxs-lookup"><span data-stu-id="5cdf0-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="5cdf0-103">Указывает, выполняет ли среда CLR сборку мусора в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="5cdf0-104">[\<конфигурация>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5cdf0-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="5cdf0-105">&nbsp;&nbsp;[\<>выполнения](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="5cdf0-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="5cdf0-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span><span class="sxs-lookup"><span data-stu-id="5cdf0-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="5cdf0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cdf0-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5cdf0-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="5cdf0-108">Attributes and elements</span></span>

<span data-ttu-id="5cdf0-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5cdf0-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5cdf0-110">Attributes</span></span>

|<span data-ttu-id="5cdf0-111">attribute</span><span class="sxs-lookup"><span data-stu-id="5cdf0-111">Attribute</span></span>|<span data-ttu-id="5cdf0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5cdf0-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="5cdf0-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-113">Required attribute.</span></span><br /><br /><span data-ttu-id="5cdf0-114">Указывает, выполняет ли среда выполнения сборку мусора параллельно.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="5cdf0-115">включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="5cdf0-115">enabled attribute</span></span>

|<span data-ttu-id="5cdf0-116">Значение</span><span class="sxs-lookup"><span data-stu-id="5cdf0-116">Value</span></span>|<span data-ttu-id="5cdf0-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5cdf0-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="5cdf0-118">Не работает сбор мусора одновременно.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="5cdf0-119">Сборка мусора выполняется параллельно.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="5cdf0-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5cdf0-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5cdf0-121">Child elements</span></span>

<span data-ttu-id="5cdf0-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5cdf0-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5cdf0-123">Parent elements</span></span>

|<span data-ttu-id="5cdf0-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="5cdf0-124">Element</span></span>|<span data-ttu-id="5cdf0-125">Описание</span><span class="sxs-lookup"><span data-stu-id="5cdf0-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="5cdf0-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="5cdf0-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5cdf0-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="5cdf0-128">Remarks</span></span>

<span data-ttu-id="5cdf0-129">До .NET Framework 4 сбор мусора на рабочих станциях поддерживал параллельный сбор мусора, который выполнял сбор мусора в фоновом режиме на отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-129">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="5cdf0-130">В .NET Framework 4 параллельный сбор мусора был заменен на фоновый GC, который также выполняет сбор мусора в фоновом режиме на отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-130">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="5cdf0-131">Начиная с .NET Framework 4.5, сбор фоновых данных стал доступен в сборе мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-131">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="5cdf0-132">Элемент **gcConcurrent** контролирует, выполняет ли время выполнения либо одновременный, либо фоновый сбор мусора, если он доступен, или же он выполняет сбор мусора на переднем плане.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-132">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="5cdf0-133">Чтобы отключить сбор фонового мусора</span><span class="sxs-lookup"><span data-stu-id="5cdf0-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="5cdf0-134">Начиная с .NET Framework 4, параллельный сбор мусора заменяется сбором фонового мусора.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-134">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="5cdf0-135">Термины *одновременно* и *фон* используются взаимозаменяемо в документации .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="5cdf0-136">Чтобы отключить сбор фонового мусора, используйте элемент **gcConcurrent,** как это обсуждается в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-136">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="5cdf0-137">По умолчанию среда выполнения использует параллельную или фоновую сборку мусора, которая оптимизирована по задержкам.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="5cdf0-138">Если приложение подразумевает активное взаимодействие с пользователем, рекомендуется использовать параллельную сборку мусора, чтобы сократить паузы в работе приложения, возникающие при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="5cdf0-139">При установке `enabled` атрибута **элемента gcConcurrent,** `false`время выполнения использует непараллельный сбор мусора, который оптимизируется для пропускной необходимости.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-139">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="5cdf0-140">Следующий файл конфигурации отравливает сбор фонового мусора:</span><span class="sxs-lookup"><span data-stu-id="5cdf0-140">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="5cdf0-141">Если в файле конфигурации машины есть параметр **gcConcurrentSetting,** он определяет значение по умолчанию для всех приложений .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-141">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="5cdf0-142">Параметр в файле конфигурации компьютера переопределяет параметр в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5cdf0-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="5cdf0-143">Для получения дополнительной информации о параллельном [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection)и фоновом [Background workstation garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)сборе мусора [Background server garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) см. [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md)</span><span class="sxs-lookup"><span data-stu-id="5cdf0-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection), [Background workstation garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection), and [Background server garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) sections in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="5cdf0-144">Пример</span><span class="sxs-lookup"><span data-stu-id="5cdf0-144">Example</span></span>

<span data-ttu-id="5cdf0-145">Следующий пример позволяет собирать фоновый мусор:</span><span class="sxs-lookup"><span data-stu-id="5cdf0-145">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="5cdf0-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5cdf0-146">See also</span></span>

- [<span data-ttu-id="5cdf0-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="5cdf0-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5cdf0-148">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="5cdf0-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5cdf0-149">Основные сведения о сборке мусора</span><span class="sxs-lookup"><span data-stu-id="5cdf0-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
