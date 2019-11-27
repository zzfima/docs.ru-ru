---
title: Гчеапкаунт, элемент
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283073"
---
# <a name="gcheapcount-element"></a><span data-ttu-id="85702-102">\<Гчеапкаунт > элемент</span><span class="sxs-lookup"><span data-stu-id="85702-102">\<GCHeapCount> element</span></span>

<span data-ttu-id="85702-103">Указывает число куч/потоков, используемых для сборки мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="85702-103">Specifies the number of heaps/threads to use for server garbage collection.</span></span>

<span data-ttu-id="85702-104">\<> конфигурации </span><span class="sxs-lookup"><span data-stu-id="85702-104">\<configuration></span></span>\
<span data-ttu-id="85702-105">&nbsp;&nbsp;\<среды выполнения > </span><span class="sxs-lookup"><span data-stu-id="85702-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="85702-106">&nbsp;&nbsp;&nbsp;&nbsp;\<Гчеапкаунт ></span><span class="sxs-lookup"><span data-stu-id="85702-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount></span></span>

## <a name="syntax"></a><span data-ttu-id="85702-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85702-107">Syntax</span></span>

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="85702-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="85702-108">Attributes and elements</span></span>

<span data-ttu-id="85702-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="85702-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="85702-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="85702-110">Attributes</span></span>

|<span data-ttu-id="85702-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="85702-111">Attribute</span></span>|<span data-ttu-id="85702-112">Описание</span><span class="sxs-lookup"><span data-stu-id="85702-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="85702-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="85702-113">Required attribute.</span></span><br /><br /><span data-ttu-id="85702-114">Указывает число куч, используемых для сборки мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="85702-114">Specifies the number of heaps to use for server garbage collection.</span></span> <span data-ttu-id="85702-115">Фактическое число куч — это минимальное количество куч, которое вы указали, и количество процессоров, которое может использовать процесс.</span><span class="sxs-lookup"><span data-stu-id="85702-115">The actual number of heaps is the minimum of the number of heaps you specify and the number of processors your process is allowed to use.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="85702-116">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="85702-116">enabled attribute</span></span>

|<span data-ttu-id="85702-117">значения</span><span class="sxs-lookup"><span data-stu-id="85702-117">Value</span></span>|<span data-ttu-id="85702-118">Описание</span><span class="sxs-lookup"><span data-stu-id="85702-118">Description</span></span>|
|-----------|-----------------|
|`nn`|<span data-ttu-id="85702-119">Число куч, используемых для сервера GC.</span><span class="sxs-lookup"><span data-stu-id="85702-119">The number of heaps to use for server GC.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="85702-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="85702-120">Child elements</span></span>

<span data-ttu-id="85702-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="85702-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="85702-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="85702-122">Parent elements</span></span>

|<span data-ttu-id="85702-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="85702-123">Element</span></span>|<span data-ttu-id="85702-124">Описание</span><span class="sxs-lookup"><span data-stu-id="85702-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="85702-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="85702-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="85702-126">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="85702-126">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="85702-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="85702-127">Remarks</span></span>

<span data-ttu-id="85702-128">По умолчанию потоки GC сервера жестко привязаны с соответствующими ПРОЦЕССОРами, чтобы существовала одна Куча сборщика мусора, один поток GC сервера и один поток GC для каждого процессора.</span><span class="sxs-lookup"><span data-stu-id="85702-128">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="85702-129">Начиная с .NET Framework 4.6.2, можно использовать элемент **гчеапкаунт** для ограничения числа куч, используемых приложением для сборки мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="85702-129">Starting with .NET Framework 4.6.2, you can use the **GCHeapCount** element to limit the number of heaps used by your application for server GC.</span></span> <span data-ttu-id="85702-130">Ограничение числа куч, используемых для сервера GC, особенно полезно для систем, работающих с несколькими экземплярами серверного приложения.</span><span class="sxs-lookup"><span data-stu-id="85702-130">Limiting the number of heaps used for server GC is particularly useful for systems that run multiple instances of a server application.</span></span>

<span data-ttu-id="85702-131">**Гчеапкаунт** обычно используется вместе с двумя другими флагами:</span><span class="sxs-lookup"><span data-stu-id="85702-131">**GCHeapCount** is typically used along with two other flags:</span></span>

- <span data-ttu-id="85702-132">[Гкноаффинитизе](gcnoaffinitize-element.md), который управляет тем, привязаны ли потоки или КУЧИ сервера GC с ЦП.</span><span class="sxs-lookup"><span data-stu-id="85702-132">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span>

- <span data-ttu-id="85702-133">[Гчеапаффинитиземаск](gcheapaffinitizemask-element.md), который управляет сходством потоков и куч сборки мусора с ЦП.</span><span class="sxs-lookup"><span data-stu-id="85702-133">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which controls the affinity of GC threads/heaps with CPUs.</span></span>

<span data-ttu-id="85702-134">Если задано значение **гчеапкаунт** и параметр **гкноаффинитизе** отключен (значение по умолчанию), то существует сходство между потоками и кучами *nn* GC и первыми *nn* процессорами.</span><span class="sxs-lookup"><span data-stu-id="85702-134">If **GCHeapCount** is set and **GCNoAffinitize** is disabled (its default setting), there is an affinity between the *nn* GC threads/heaps and the first *nn* processors.</span></span> <span data-ttu-id="85702-135">С помощью элемента **гчеапаффинитиземаск** можно указать, какие процессоры используются в кучах сервера процесса.</span><span class="sxs-lookup"><span data-stu-id="85702-135">You can use the **GCHeapAffinitizeMask** element to specify which processors are used by the process's server GC heaps.</span></span> <span data-ttu-id="85702-136">В противном случае, если в системе выполняется несколько серверных процессов, их использование процессора будет перекрываться.</span><span class="sxs-lookup"><span data-stu-id="85702-136">Otherwise, if multiple server processes are running on a system, their processor usage will overlap.</span></span>

<span data-ttu-id="85702-137">Если задано значение **гчеапкаунт** и включен параметр **гкноаффинитизе** , сборщик мусора ограничивает количество процессоров, используемых для GC сервера, но не привязать КУЧИ и процессоры GC.</span><span class="sxs-lookup"><span data-stu-id="85702-137">If **GCHeapCount** is set and **GCNoAffinitize** is enabled, the garbage collector limits the number of processors used for server GC but does not affinitize GC heaps and processors.</span></span>

## <a name="example"></a><span data-ttu-id="85702-138">Пример</span><span class="sxs-lookup"><span data-stu-id="85702-138">Example</span></span>

<span data-ttu-id="85702-139">В следующем примере показано, что приложение использует серверную сборку мусора с 10 кучами и потоками.</span><span class="sxs-lookup"><span data-stu-id="85702-139">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="85702-140">Так как вы не хотите, чтобы эти кучи перекрывались с кучами из других приложений, работающих в системе, используйте **гчеапаффинитиземаск** , чтобы указать, что процесс должен использовать процессоры от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="85702-140">Since you don't want those heaps to overlap with heaps from other applications running on the system, you use the **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

<span data-ttu-id="85702-141">В следующем примере не привязать потоки сервера GC и ограничивает число куч/потоков GC до 10.</span><span class="sxs-lookup"><span data-stu-id="85702-141">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="85702-142">См. также</span><span class="sxs-lookup"><span data-stu-id="85702-142">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="85702-143">Гкноаффинитизе, элемент</span><span class="sxs-lookup"><span data-stu-id="85702-143">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="85702-144">Гчеапаффинитиземаск, элемент</span><span class="sxs-lookup"><span data-stu-id="85702-144">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="85702-145">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="85702-145">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="85702-146">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="85702-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="85702-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="85702-147">Configuration File Schema</span></span>](../index.md)
