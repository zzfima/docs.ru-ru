---
title: gcConcurrent, элемент
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
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969234"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="3503c-102">\<gcConcurrent > элемент</span><span class="sxs-lookup"><span data-stu-id="3503c-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="3503c-103">Указывает, выполняет ли среда CLR сборку мусора в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="3503c-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="3503c-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3503c-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="3503c-105">[> среды выполнения\<](runtime-element.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="3503c-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="3503c-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent ></span><span class="sxs-lookup"><span data-stu-id="3503c-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="3503c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3503c-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3503c-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="3503c-108">Attributes and elements</span></span>

<span data-ttu-id="3503c-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3503c-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3503c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3503c-110">Attributes</span></span>

|<span data-ttu-id="3503c-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3503c-111">Attribute</span></span>|<span data-ttu-id="3503c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3503c-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="3503c-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="3503c-113">Required attribute.</span></span><br /><br /><span data-ttu-id="3503c-114">Указывает, выполняет ли среда выполнения сборку мусора параллельно.</span><span class="sxs-lookup"><span data-stu-id="3503c-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="3503c-115">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="3503c-115">enabled attribute</span></span>

|<span data-ttu-id="3503c-116">значения</span><span class="sxs-lookup"><span data-stu-id="3503c-116">Value</span></span>|<span data-ttu-id="3503c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="3503c-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="3503c-118">Не выполняется параллельное выполнение сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3503c-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="3503c-119">Сборка мусора выполняется параллельно.</span><span class="sxs-lookup"><span data-stu-id="3503c-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="3503c-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3503c-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3503c-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3503c-121">Child elements</span></span>

<span data-ttu-id="3503c-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3503c-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3503c-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3503c-123">Parent elements</span></span>

|<span data-ttu-id="3503c-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="3503c-124">Element</span></span>|<span data-ttu-id="3503c-125">Описание</span><span class="sxs-lookup"><span data-stu-id="3503c-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="3503c-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3503c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="3503c-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="3503c-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3503c-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="3503c-128">Remarks</span></span>

<span data-ttu-id="3503c-129">До .NET Framework 4 сборка мусора рабочей станции поддерживала параллельную сборку мусора, которая выполняла сборку мусора в фоновом режиме в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="3503c-129">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="3503c-130">В .NET Framework 4 параллельная сборка мусора была заменена фоновым GC, который также выполняет сборку мусора в фоновом режиме в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="3503c-130">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="3503c-131">Начиная с .NET Framework 4,5, фоновая коллекция стала доступна в процессе сборки мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="3503c-131">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="3503c-132">Элемент **gcConcurrent** определяет, выполняет ли среда выполнения параллельную или фоновую сборку мусора, если она доступна, или же она выполняет сборку мусора на переднем плане.</span><span class="sxs-lookup"><span data-stu-id="3503c-132">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="3503c-133">Отключение фоновой сборки мусора</span><span class="sxs-lookup"><span data-stu-id="3503c-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="3503c-134">Начиная с .NET Framework 4, параллельная сборка мусора заменяется фоновой сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="3503c-134">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="3503c-135">*Одновременные* и *фоновые* термины в документации по .NET Framework используются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="3503c-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="3503c-136">Чтобы отключить фоновую сборку мусора, используйте элемент **gcConcurrent** , как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="3503c-136">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="3503c-137">По умолчанию среда выполнения использует параллельную или фоновую сборку мусора, которая оптимизирована по задержкам.</span><span class="sxs-lookup"><span data-stu-id="3503c-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="3503c-138">Если приложение подразумевает активное взаимодействие с пользователем, рекомендуется использовать параллельную сборку мусора, чтобы сократить паузы в работе приложения, возникающие при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="3503c-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="3503c-139">Если для атрибута `enabled` элемента **gcConcurrent** задано значение `false`, среда выполнения использует непараллельную сборку мусора, оптимизированную для пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="3503c-139">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="3503c-140">Следующий файл конфигурации отключает фоновую сборку мусора:</span><span class="sxs-lookup"><span data-stu-id="3503c-140">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="3503c-141">Если в файле конфигурации компьютера есть параметр **гкконкуррентсеттинг** , он определяет значение по умолчанию для всех .NET Framework приложений.</span><span class="sxs-lookup"><span data-stu-id="3503c-141">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="3503c-142">Параметр в файле конфигурации компьютера переопределяет параметр в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="3503c-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="3503c-143">Дополнительные сведения о параллельной и фоновой сборке мусора см. в разделах [параллельная сборка мусора](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection), [Фоновая сборка мусора рабочей станции](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)и [сборка мусора фонового сервера](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) в разделе [основы сборки мусора](../../../../standard/garbage-collection/fundamentals.md) .</span><span class="sxs-lookup"><span data-stu-id="3503c-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection), [Background workstation garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection), and [Background server garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) sections in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="3503c-144">Пример</span><span class="sxs-lookup"><span data-stu-id="3503c-144">Example</span></span>

<span data-ttu-id="3503c-145">В следующем примере включается фоновая сборка мусора:</span><span class="sxs-lookup"><span data-stu-id="3503c-145">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="3503c-146">См. также</span><span class="sxs-lookup"><span data-stu-id="3503c-146">See also</span></span>

- [<span data-ttu-id="3503c-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="3503c-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3503c-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="3503c-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3503c-149">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="3503c-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
