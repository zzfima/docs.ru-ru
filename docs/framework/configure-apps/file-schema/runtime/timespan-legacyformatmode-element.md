---
title: Элемент <TimeSpan_LegacyFormatMode>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e265fd1de6047cd53b0f8d1c20c8a9e87b3e813
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689666"
---
# <a name="timespanlegacyformatmode-element"></a><span data-ttu-id="e774c-102">\<TimeSpan_LegacyFormatMode > элемент</span><span class="sxs-lookup"><span data-stu-id="e774c-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="e774c-103">Определяет, сохраняет ли среда выполнения устаревшее поведение в операциях с форматирования <xref:System.TimeSpan?displayProperty=nameWithType> значения.</span><span class="sxs-lookup"><span data-stu-id="e774c-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

<span data-ttu-id="e774c-104">\<Конфигурация > \\</span><span class="sxs-lookup"><span data-stu-id="e774c-104">\<configuration>\\</span></span>
<span data-ttu-id="e774c-105">\<Среда выполнения > \\</span><span class="sxs-lookup"><span data-stu-id="e774c-105">\<runtime>\\</span></span>
<span data-ttu-id="e774c-106">\<TimeSpan_LegacyFormatMode ></span><span class="sxs-lookup"><span data-stu-id="e774c-106">\<TimeSpan_LegacyFormatMode></span></span>

## <a name="syntax"></a><span data-ttu-id="e774c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e774c-107">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e774c-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e774c-108">Attributes and Elements</span></span>

<span data-ttu-id="e774c-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e774c-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e774c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e774c-110">Attributes</span></span>

|<span data-ttu-id="e774c-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e774c-111">Attribute</span></span>|<span data-ttu-id="e774c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e774c-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="e774c-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e774c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e774c-114">Указывает, использует ли среда выполнения устаревшее поведение форматирования с <xref:System.TimeSpan?displayProperty=nameWithType> значения.</span><span class="sxs-lookup"><span data-stu-id="e774c-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="e774c-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="e774c-115">enabled Attribute</span></span>

|<span data-ttu-id="e774c-116">Значение</span><span class="sxs-lookup"><span data-stu-id="e774c-116">Value</span></span>|<span data-ttu-id="e774c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="e774c-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="e774c-118">Среда выполнения не восстанавливает устаревшее поведение форматирования.</span><span class="sxs-lookup"><span data-stu-id="e774c-118">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="e774c-119">Среда выполнения восстанавливает устаревшее поведение форматирования.</span><span class="sxs-lookup"><span data-stu-id="e774c-119">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e774c-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e774c-120">Child Elements</span></span>

<span data-ttu-id="e774c-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e774c-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e774c-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e774c-122">Parent Elements</span></span>

|<span data-ttu-id="e774c-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="e774c-123">Element</span></span>|<span data-ttu-id="e774c-124">Описание</span><span class="sxs-lookup"><span data-stu-id="e774c-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="e774c-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e774c-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="e774c-126">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e774c-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e774c-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="e774c-127">Remarks</span></span>

<span data-ttu-id="e774c-128">Начиная с .NET Framework 4, <xref:System.TimeSpan?displayProperty=nameWithType> структура реализует <xref:System.IFormattable> интерфейс и поддерживает операций со строками формата стандартные и настраиваемые форматирования.</span><span class="sxs-lookup"><span data-stu-id="e774c-128">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="e774c-129">Если метод синтаксического анализа встречается описатель неподдерживаемый формат или строка формата, он выдает <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="e774c-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="e774c-130">В предыдущих версиях .NET Framework <xref:System.TimeSpan> структуры не реализовал <xref:System.IFormattable> и не поддерживает строки формата.</span><span class="sxs-lookup"><span data-stu-id="e774c-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="e774c-131">Тем не менее, многие разработчики ошибочно полагают, что <xref:System.TimeSpan> поддерживали набор строк формата, которые использовались в [составного форматирования операций](../../../../../docs/standard/base-types/composite-formatting.md) с помощью методов, таких как <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e774c-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../../docs/standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e774c-132">Как правило если тип реализует <xref:System.IFormattable> и поддерживает формат строки, вызовы методов форматирования с неподдерживаемый формат строки обычно throw <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="e774c-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="e774c-133">Тем не менее так как <xref:System.TimeSpan> не реализовал <xref:System.IFormattable>, среда выполнения, игнорируется строка форматирования и вместо этого вызов <xref:System.TimeSpan.ToString?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="e774c-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e774c-134">Это означает, что, несмотря на то, что строки формата не оказывает никакого влияния на операции форматирования, их наличие не привели к <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="e774c-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="e774c-135">Для случаев, в которых устаревший код передает составного форматирования метода и Недопустимая строка форматирования, а не удается заново скомпилировать этот код, можно использовать `<TimeSpan_LegacyFormatMode>` элемента для восстановления предыдущих версий <xref:System.TimeSpan> поведение.</span><span class="sxs-lookup"><span data-stu-id="e774c-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="e774c-136">При задании `enabled` атрибут этого элемента к `true`, составного форматирования результаты метода в вызове <xref:System.TimeSpan.ToString?displayProperty=nameWithType> вместо <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>и <xref:System.FormatException> не создается.</span><span class="sxs-lookup"><span data-stu-id="e774c-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="e774c-137">Пример</span><span class="sxs-lookup"><span data-stu-id="e774c-137">Example</span></span>

<span data-ttu-id="e774c-138">В следующем примере создается <xref:System.TimeSpan> объекта и предпринимает попытку отформатировать его с <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> метод с использованием строки стандартного формата, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e774c-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="e774c-139">При выполнении примера на .NET Framework 3.5 или более ранней версии, отображается следующий результат:</span><span class="sxs-lookup"><span data-stu-id="e774c-139">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```
12:30:45
```

<span data-ttu-id="e774c-140">Они сильно отличаются от выходных данных при выполнении примера на .NET Framework 4 или более поздней версии:</span><span class="sxs-lookup"><span data-stu-id="e774c-140">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```
Invalid Format
```

<span data-ttu-id="e774c-141">Тем не менее если добавить следующий файл конфигурации в каталог примеров и затем запустить пример в .NET Framework 4 или более поздней версии, выходные данные идентичны данным, созданным примером при его запуске в .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="e774c-141">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e774c-142">См. также</span><span class="sxs-lookup"><span data-stu-id="e774c-142">See also</span></span>

- [<span data-ttu-id="e774c-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e774c-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="e774c-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e774c-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
