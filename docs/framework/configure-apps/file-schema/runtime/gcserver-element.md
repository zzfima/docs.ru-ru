---
title: gcServer, элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: 8eab5e36bab90510aff4f1a3e15328197ac59ed7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968949"
---
# <a name="gcserver-element"></a><span data-ttu-id="789d3-102">\<gcServer > элемент</span><span class="sxs-lookup"><span data-stu-id="789d3-102">\<gcServer> element</span></span>

<span data-ttu-id="789d3-103">Указывает, выполняет ли среда CLR сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="789d3-103">Specifies whether the common language runtime runs server garbage collection.</span></span>

<span data-ttu-id="789d3-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="789d3-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="789d3-105">[> среды выполнения\<](runtime-element.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="789d3-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="789d3-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer ></span><span class="sxs-lookup"><span data-stu-id="789d3-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer></span></span>

## <a name="syntax"></a><span data-ttu-id="789d3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="789d3-107">Syntax</span></span>

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="789d3-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="789d3-108">Attributes and elements</span></span>

<span data-ttu-id="789d3-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="789d3-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="789d3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="789d3-110">Attributes</span></span>

|<span data-ttu-id="789d3-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="789d3-111">Attribute</span></span>|<span data-ttu-id="789d3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="789d3-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="789d3-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="789d3-113">Required attribute.</span></span><br /><br /><span data-ttu-id="789d3-114">Указывает, выполняет ли среда выполнения сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="789d3-114">Specifies whether the runtime runs server garbage collection.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="789d3-115">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="789d3-115">enabled attribute</span></span>

|<span data-ttu-id="789d3-116">значения</span><span class="sxs-lookup"><span data-stu-id="789d3-116">Value</span></span>|<span data-ttu-id="789d3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="789d3-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="789d3-118">Не выполняет сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="789d3-118">Does not run server garbage collection.</span></span> <span data-ttu-id="789d3-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="789d3-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="789d3-120">Выполняет сборку мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="789d3-120">Runs server garbage collection.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="789d3-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="789d3-121">Child elements</span></span>

<span data-ttu-id="789d3-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="789d3-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="789d3-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="789d3-123">Parent elements</span></span>

|<span data-ttu-id="789d3-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="789d3-124">Element</span></span>|<span data-ttu-id="789d3-125">Описание</span><span class="sxs-lookup"><span data-stu-id="789d3-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="789d3-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="789d3-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="789d3-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="789d3-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="789d3-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="789d3-128">Remarks</span></span>

<span data-ttu-id="789d3-129">Среда CLR поддерживает два типа сборки мусора: сборку мусора рабочей станции, которая доступна во всех системах, и сборку мусора сервера, которая доступна в многопроцессорных системах.</span><span class="sxs-lookup"><span data-stu-id="789d3-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="789d3-130">Используйте элемент **gcServer** для управления типом сборки мусора, ВЫПОЛНЯЕМой средой CLR.</span><span class="sxs-lookup"><span data-stu-id="789d3-130">Use the **gcServer** element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="789d3-131">Используйте свойство <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>, чтобы определить, включена ли сборка мусора сервера.</span><span class="sxs-lookup"><span data-stu-id="789d3-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>

<span data-ttu-id="789d3-132">Для однопроцессорных компьютеров сборка мусора рабочей станции по умолчанию должна быть самым быстрым вариантом.</span><span class="sxs-lookup"><span data-stu-id="789d3-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="789d3-133">Для двухпроцессорных компьютеров можно использовать сборку мусора как рабочей станции, так и сервера.</span><span class="sxs-lookup"><span data-stu-id="789d3-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="789d3-134">Сборка мусора сервера должно быть самым быстрым вариантом при наличии более двух процессоров.</span><span class="sxs-lookup"><span data-stu-id="789d3-134">Server garbage collection should be the fastest option for more than two processors.</span></span> <span data-ttu-id="789d3-135">Чаще всего многопроцессорные серверные системы отключают серверную сборку мусора и используют СБОРЩИКи рабочих станций, если на одном компьютере работает много экземпляров серверного приложения.</span><span class="sxs-lookup"><span data-stu-id="789d3-135">Most commonly, multiprocessor server systems disable server GC and use workstation GC instead when many instances of a server app run on the same machine.</span></span>

<span data-ttu-id="789d3-136">Этот элемент может использоваться только в файле конфигурации приложения; в файле конфигурации компьютера он игнорируется.</span><span class="sxs-lookup"><span data-stu-id="789d3-136">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="789d3-137">В платформе .NET Framework версии 4 и более ранних версиях параллельная сборка мусора недоступна, если включена серверная сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="789d3-137">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="789d3-138">С версии .NET Framework 4.5 серверная сборка мусора является параллельной.</span><span class="sxs-lookup"><span data-stu-id="789d3-138">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="789d3-139">Чтобы использовать непараллельную сборку мусора сервера, присвойте элементу **gcServer** значение `true` а [элемент gcConcurrent](gcconcurrent-element.md) — `false`.</span><span class="sxs-lookup"><span data-stu-id="789d3-139">To use non-concurrent server garbage collection, set the **gcServer** element to `true` and the [gcConcurrent element](gcconcurrent-element.md) to `false`.</span></span>

<span data-ttu-id="789d3-140">Начиная с .NET Framework 4.6.2 можно также использовать следующие элементы для настройки GC сервера:</span><span class="sxs-lookup"><span data-stu-id="789d3-140">Starting with .NET Framework 4.6.2, you can also use the following elements to configure server GC:</span></span>

- <span data-ttu-id="789d3-141">[Гкноаффинитизе](gcnoaffinitize-element.md), который указывает, существует ли сходство между кучами и процессорами серверной сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="789d3-141">[GCNoAffinitize](gcnoaffinitize-element.md), which specifies whether there is an affinity between server GC heaps and processors.</span></span> <span data-ttu-id="789d3-142">По умолчанию для каждого процессора существует одна куча сервера GC.</span><span class="sxs-lookup"><span data-stu-id="789d3-142">By default, there is one server GC heap for each processor.</span></span>

- <span data-ttu-id="789d3-143">[Гчеапкаунт](gcheapcount-element.md), ограничивающее количество куч, используемых процессом.</span><span class="sxs-lookup"><span data-stu-id="789d3-143">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by a process.</span></span>

- <span data-ttu-id="789d3-144">[Гчеапаффинитиземаск](gcheapaffinitizemask-element.md), который определяет сходство между доступными кучами сервера GC и отдельными процессорами.</span><span class="sxs-lookup"><span data-stu-id="789d3-144">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which defines the affinity between the available server GC heaps and individual processors.</span></span>

## <a name="example"></a><span data-ttu-id="789d3-145">Пример</span><span class="sxs-lookup"><span data-stu-id="789d3-145">Example</span></span>

<span data-ttu-id="789d3-146">В следующем примере включается сборка мусора сервера:</span><span class="sxs-lookup"><span data-stu-id="789d3-146">The following example enables server garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="789d3-147">См. также</span><span class="sxs-lookup"><span data-stu-id="789d3-147">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="789d3-148">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="789d3-148">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="789d3-149">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="789d3-149">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="789d3-150">Отключение параллельной сборки мусора</span><span class="sxs-lookup"><span data-stu-id="789d3-150">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
