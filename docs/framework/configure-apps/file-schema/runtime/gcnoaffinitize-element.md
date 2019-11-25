---
title: Гкноаффинитизе, элемент
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 4031ff19131c905072696837d1622dbb6e54ae61
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978417"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="12861-102">\<Гкноаффинитизе > элемент</span><span class="sxs-lookup"><span data-stu-id="12861-102">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="12861-103">Указывает, следует ли привязать потоки сервера GC с ЦП.</span><span class="sxs-lookup"><span data-stu-id="12861-103">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

<span data-ttu-id="12861-104">\<> конфигурации </span><span class="sxs-lookup"><span data-stu-id="12861-104">\<configuration></span></span>\
<span data-ttu-id="12861-105">&nbsp;&nbsp;\<среды выполнения > </span><span class="sxs-lookup"><span data-stu-id="12861-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="12861-106">&nbsp;&nbsp;&nbsp;&nbsp;\<Гкноаффинитизе ></span><span class="sxs-lookup"><span data-stu-id="12861-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize></span></span>

## <a name="syntax"></a><span data-ttu-id="12861-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12861-107">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="12861-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="12861-108">Attributes and elements</span></span>

<span data-ttu-id="12861-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="12861-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="12861-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="12861-110">Attributes</span></span>

|<span data-ttu-id="12861-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="12861-111">Attribute</span></span>|<span data-ttu-id="12861-112">Описание</span><span class="sxs-lookup"><span data-stu-id="12861-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="12861-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="12861-113">Required attribute.</span></span><br /><br /><span data-ttu-id="12861-114">Указывает, привязаны ли потоки или кучи серверной сборки мусора с процессорами, доступными на компьютере.</span><span class="sxs-lookup"><span data-stu-id="12861-114">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="12861-115">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="12861-115">enabled attribute</span></span>

|<span data-ttu-id="12861-116">значения</span><span class="sxs-lookup"><span data-stu-id="12861-116">Value</span></span>|<span data-ttu-id="12861-117">Описание</span><span class="sxs-lookup"><span data-stu-id="12861-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="12861-118">Потоки GC сервера аффинитизес с ЦП.</span><span class="sxs-lookup"><span data-stu-id="12861-118">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="12861-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="12861-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="12861-120">Не привязать потоки GC сервера с процессорами.</span><span class="sxs-lookup"><span data-stu-id="12861-120">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="12861-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="12861-121">Child elements</span></span>

<span data-ttu-id="12861-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="12861-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="12861-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="12861-123">Parent elements</span></span>

|<span data-ttu-id="12861-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="12861-124">Element</span></span>|<span data-ttu-id="12861-125">Описание</span><span class="sxs-lookup"><span data-stu-id="12861-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="12861-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="12861-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="12861-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="12861-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="12861-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="12861-128">Remarks</span></span>

<span data-ttu-id="12861-129">По умолчанию потоки GC сервера жестко привязаны с соответствующими процессорами.</span><span class="sxs-lookup"><span data-stu-id="12861-129">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="12861-130">Каждый из доступных процессоров системы имеет собственную кучу сборщика мусора и поток.</span><span class="sxs-lookup"><span data-stu-id="12861-130">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="12861-131">Обычно это предпочтительный параметр, так как он оптимизирует использование кэша.</span><span class="sxs-lookup"><span data-stu-id="12861-131">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="12861-132">Начиная с .NET Framework 4.6.2, установив атрибут `enabled` элемента **гкноаффинитизе** в значение `false`, можно указать, что потоки GC сервера и ЦП не должны быть тесно связаны.</span><span class="sxs-lookup"><span data-stu-id="12861-132">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `false`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="12861-133">Можно указать только элемент конфигурации **гкноаффинитизе** , чтобы не ПРИВЯЗАТЬ потоки GC сервера с процессорами.</span><span class="sxs-lookup"><span data-stu-id="12861-133">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="12861-134">Кроме того, его можно использовать вместе с элементом [гчеапкаунт](gcheapcount-element.md) для управления числом куч и потоков GC, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="12861-134">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="12861-135">Если атрибут `enabled` элемента **гкноаффинитизе** имеет `false` (значение по умолчанию), можно также использовать элемент [гчеапкаунт](gcheapcount-element.md) , чтобы указать количество потоков и куч GC вместе с элементом [гчеапаффинитиземаск](gcheapaffinitizemask-element.md) , чтобы указать процессоры, к которым будут привязаныся потоки и кучи GC.</span><span class="sxs-lookup"><span data-stu-id="12861-135">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="12861-136">Пример</span><span class="sxs-lookup"><span data-stu-id="12861-136">Example</span></span>

<span data-ttu-id="12861-137">В следующем примере не привязать потоки GC сервера.</span><span class="sxs-lookup"><span data-stu-id="12861-137">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="12861-138">В следующем примере не привязать потоки сервера GC и ограничивает число куч/потоков GC до 10:</span><span class="sxs-lookup"><span data-stu-id="12861-138">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="12861-139">См. также</span><span class="sxs-lookup"><span data-stu-id="12861-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="12861-140">Гчеапаффинитиземаск, элемент</span><span class="sxs-lookup"><span data-stu-id="12861-140">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="12861-141">Гчеапкаунт, элемент</span><span class="sxs-lookup"><span data-stu-id="12861-141">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="12861-142">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="12861-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="12861-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="12861-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="12861-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="12861-144">Configuration File Schema</span></span>](../index.md)
