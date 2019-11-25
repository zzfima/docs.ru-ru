---
title: Гчеапаффинитиземаск, элемент
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978423"
---
# <a name="gcheapaffinitizemask-element"></a><span data-ttu-id="9d019-102">\<Гчеапаффинитиземаск > элемент</span><span class="sxs-lookup"><span data-stu-id="9d019-102">\<GCHeapAffinitizeMask> element</span></span>

<span data-ttu-id="9d019-103">Определяет сходство между кучами сборщика мусора и отдельными процессорами.</span><span class="sxs-lookup"><span data-stu-id="9d019-103">Defines the affinity between GC heaps and individual processors.</span></span>

<span data-ttu-id="9d019-104">\<> конфигурации </span><span class="sxs-lookup"><span data-stu-id="9d019-104">\<configuration></span></span>\
<span data-ttu-id="9d019-105">&nbsp;&nbsp;\<среды выполнения > </span><span class="sxs-lookup"><span data-stu-id="9d019-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="9d019-106">&nbsp;&nbsp;&nbsp;&nbsp;\<Гчеапаффинитиземаск ></span><span class="sxs-lookup"><span data-stu-id="9d019-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask></span></span>

## <a name="syntax"></a><span data-ttu-id="9d019-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d019-107">Syntax</span></span>

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9d019-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="9d019-108">Attributes and elements</span></span>

<span data-ttu-id="9d019-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9d019-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d019-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9d019-110">Attributes</span></span>

|<span data-ttu-id="9d019-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9d019-111">Attribute</span></span>|<span data-ttu-id="9d019-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9d019-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="9d019-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9d019-113">Required attribute.</span></span><br /><br /><span data-ttu-id="9d019-114">Указывает сходство между кучами сборщика мусора и отдельными процессорами.</span><span class="sxs-lookup"><span data-stu-id="9d019-114">Specifies the affinity between GC heaps and individual processors.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="9d019-115">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="9d019-115">enabled attribute</span></span>

|<span data-ttu-id="9d019-116">значения</span><span class="sxs-lookup"><span data-stu-id="9d019-116">Value</span></span>|<span data-ttu-id="9d019-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9d019-117">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="9d019-118">Десятичное значение, которое образует битовую маску для определения сходства между кучами сервера GC и отдельными процессорами.</span><span class="sxs-lookup"><span data-stu-id="9d019-118">A decimal value that forms a bitmask defining the affinity between server GC heaps and individual processors.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="9d019-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9d019-119">Child elements</span></span>

<span data-ttu-id="9d019-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9d019-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9d019-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9d019-121">Parent elements</span></span>

|<span data-ttu-id="9d019-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="9d019-122">Element</span></span>|<span data-ttu-id="9d019-123">Описание</span><span class="sxs-lookup"><span data-stu-id="9d019-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="9d019-124">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d019-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="9d019-125">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="9d019-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9d019-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="9d019-126">Remarks</span></span>

<span data-ttu-id="9d019-127">По умолчанию потоки GC сервера жестко привязаны с соответствующими ПРОЦЕССОРами, чтобы существовала одна Куча сборщика мусора, один поток GC сервера и один поток GC для каждого процессора.</span><span class="sxs-lookup"><span data-stu-id="9d019-127">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="9d019-128">Начиная с .NET Framework 4.6.2, можно использовать элемент **гчеапаффинитиземаск** для управления соответствием между кучами и процессорами сервера GC, если число куч ограничено элементом **гчеапкаунт** .</span><span class="sxs-lookup"><span data-stu-id="9d019-128">Starting with .NET Framework 4.6.2, you can use the **GCHeapAffinitizeMask** element to control the affinity between server GC heaps and processors when the number of heaps is limited by the **GCHeapCount** element.</span></span>

<span data-ttu-id="9d019-129">**Гчеапаффинитиземаск** обычно используется вместе с двумя другими флагами:</span><span class="sxs-lookup"><span data-stu-id="9d019-129">**GCHeapAffinitizeMask** is typically used along with two other flags:</span></span>

- <span data-ttu-id="9d019-130">[Гкноаффинитизе](gcnoaffinitize-element.md), который управляет тем, привязаны ли потоки или КУЧИ сервера GC с ЦП.</span><span class="sxs-lookup"><span data-stu-id="9d019-130">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span> <span data-ttu-id="9d019-131">Для использования параметра **гчеапаффинитиземаск** атрибут `enabled` элемента [гкноаффинитизе](gcnoaffinitize-element.md) должен быть `false` (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9d019-131">The `enabled` attribute of the [GCNoAffinitize](gcnoaffinitize-element.md) element must be `false` (its default value) for the **GCHeapAffinitizeMask** setting to be used.</span></span>

- <span data-ttu-id="9d019-132">[Гчеапкаунт](gcheapcount-element.md), ограничивающее количество куч, используемых процессом для сервера GC.</span><span class="sxs-lookup"><span data-stu-id="9d019-132">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by the process for server GC.</span></span> <span data-ttu-id="9d019-133">По умолчанию для каждого процессора существует одна куча.</span><span class="sxs-lookup"><span data-stu-id="9d019-133">By default, there is one heap for each processor.</span></span>

<span data-ttu-id="9d019-134">**nnnn** — это битовая маска, выраженная в виде десятичного значения.</span><span class="sxs-lookup"><span data-stu-id="9d019-134">**nnnn** is a bit mask expressed as a decimal value.</span></span> <span data-ttu-id="9d019-135">Бит 0 байт 0 представляет процессор 0, бит 1 байт 0 представляет процессор 1 и т. д.</span><span class="sxs-lookup"><span data-stu-id="9d019-135">Bit 0 of byte 0 represents processor 0, bit 1 of byte 0 represents processor 1, and so on.</span></span> <span data-ttu-id="9d019-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="9d019-136">For example:</span></span>

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

<span data-ttu-id="9d019-137">Значение 1023 — 0x3FF или 0011 1111 1111b.</span><span class="sxs-lookup"><span data-stu-id="9d019-137">A value of 1023 is 0x3FF or 0011 1111 1111b.</span></span> <span data-ttu-id="9d019-138">Процесс использует 10 процессоров, от процессора 0 до процессора 9.</span><span class="sxs-lookup"><span data-stu-id="9d019-138">The process uses 10 processors, from processor 0 through processor 9.</span></span>

## <a name="example"></a><span data-ttu-id="9d019-139">Пример</span><span class="sxs-lookup"><span data-stu-id="9d019-139">Example</span></span>

<span data-ttu-id="9d019-140">В следующем примере показано, что приложение использует серверную сборку мусора с 10 кучами и потоками.</span><span class="sxs-lookup"><span data-stu-id="9d019-140">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="9d019-141">Так как вы не хотите, чтобы эти кучи перекрывались с кучами из других приложений, работающих в системе, используйте **гчеапаффинитиземаск** , чтобы указать, что процесс должен использовать процессоры от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="9d019-141">Since you don't want those heaps to overlap with heaps from other applications running on the system, use **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="9d019-142">См. также</span><span class="sxs-lookup"><span data-stu-id="9d019-142">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9d019-143">Гкноаффинитизе, элемент</span><span class="sxs-lookup"><span data-stu-id="9d019-143">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="9d019-144">Гчеапкаунт, элемент</span><span class="sxs-lookup"><span data-stu-id="9d019-144">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="9d019-145">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="9d019-145">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="9d019-146">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="9d019-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9d019-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="9d019-147">Configuration File Schema</span></span>](../index.md)
