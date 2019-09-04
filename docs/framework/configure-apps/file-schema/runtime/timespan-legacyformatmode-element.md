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
ms.openlocfilehash: 64bf667c5c9bc20db14f08f18fa6f4f84fa12a24
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252253"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="912dc-102">\<Элемент > TimeSpan_LegacyFormatMode</span><span class="sxs-lookup"><span data-stu-id="912dc-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="912dc-103">Определяет, сохраняет ли среда выполнения устаревшее поведение в операциях <xref:System.TimeSpan?displayProperty=nameWithType> форматирования со значениями.</span><span class="sxs-lookup"><span data-stu-id="912dc-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

<span data-ttu-id="912dc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="912dc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="912dc-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="912dc-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="912dc-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<TimeSpan_LegacyFormatMode >**</span><span class="sxs-lookup"><span data-stu-id="912dc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="912dc-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="912dc-107">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="912dc-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="912dc-108">Attributes and Elements</span></span>

<span data-ttu-id="912dc-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="912dc-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="912dc-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="912dc-110">Attributes</span></span>

|<span data-ttu-id="912dc-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="912dc-111">Attribute</span></span>|<span data-ttu-id="912dc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="912dc-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="912dc-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="912dc-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="912dc-114">Указывает, использует ли среда выполнения устаревшее поведение <xref:System.TimeSpan?displayProperty=nameWithType> форматирования со значениями.</span><span class="sxs-lookup"><span data-stu-id="912dc-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="912dc-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="912dc-115">enabled Attribute</span></span>

|<span data-ttu-id="912dc-116">Значение</span><span class="sxs-lookup"><span data-stu-id="912dc-116">Value</span></span>|<span data-ttu-id="912dc-117">Описание</span><span class="sxs-lookup"><span data-stu-id="912dc-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="912dc-118">Среда выполнения не восстанавливает устаревшее поведение форматирования.</span><span class="sxs-lookup"><span data-stu-id="912dc-118">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="912dc-119">Среда выполнения восстанавливает устаревшее поведение форматирования.</span><span class="sxs-lookup"><span data-stu-id="912dc-119">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="912dc-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="912dc-120">Child Elements</span></span>

<span data-ttu-id="912dc-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="912dc-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="912dc-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="912dc-122">Parent Elements</span></span>

|<span data-ttu-id="912dc-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="912dc-123">Element</span></span>|<span data-ttu-id="912dc-124">Описание</span><span class="sxs-lookup"><span data-stu-id="912dc-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="912dc-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="912dc-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="912dc-126">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="912dc-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="912dc-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="912dc-127">Remarks</span></span>

<span data-ttu-id="912dc-128">Начиная с .NET Framework 4 <xref:System.TimeSpan?displayProperty=nameWithType> структура <xref:System.IFormattable> реализует интерфейс и поддерживает операции форматирования со стандартными и пользовательскими строками формата.</span><span class="sxs-lookup"><span data-stu-id="912dc-128">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="912dc-129">Если метод синтаксического анализа обнаруживает неподдерживаемый описатель формата или строку формата, он создает исключение <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="912dc-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="912dc-130">В предыдущих версиях .NET Framework <xref:System.TimeSpan> структура не реализовала <xref:System.IFormattable> и не поддерживала строки формата.</span><span class="sxs-lookup"><span data-stu-id="912dc-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="912dc-131">Однако многие разработчики ошибочно предполагали, <xref:System.TimeSpan> что поддерживало набор строк формата и использовали их в [операциях составного форматирования](../../../../standard/base-types/composite-formatting.md) с помощью таких <xref:System.String.Format%2A?displayProperty=nameWithType>методов, как.</span><span class="sxs-lookup"><span data-stu-id="912dc-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="912dc-132">Обычно, если тип реализует <xref:System.IFormattable> и поддерживает строки формата, вызовы методов форматирования с неподдерживаемыми строками формата обычно <xref:System.FormatException>создают исключение.</span><span class="sxs-lookup"><span data-stu-id="912dc-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="912dc-133">Однако, поскольку <xref:System.TimeSpan> не реализуется <xref:System.IFormattable>, среда выполнения игнорирует <xref:System.TimeSpan.ToString?displayProperty=nameWithType> строку формата и вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="912dc-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="912dc-134">Это означает, что, хотя строки формата не оказывают влияния на операцию форматирования, их присутствие не привело к <xref:System.FormatException>созданию.</span><span class="sxs-lookup"><span data-stu-id="912dc-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="912dc-135">Для случаев, когда устаревший код передает метод составного форматирования и недопустимую строку формата, и этот код нельзя перекомпилировать, можно использовать `<TimeSpan_LegacyFormatMode>` элемент для восстановления прежнего <xref:System.TimeSpan> поведения.</span><span class="sxs-lookup"><span data-stu-id="912dc-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="912dc-136">Если `enabled` атрибуту этого `true`элемента присвоить значение, метод составного форматирования приводит к <xref:System.TimeSpan.ToString?displayProperty=nameWithType> вызову <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, а не, а <xref:System.FormatException> исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="912dc-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="912dc-137">Пример</span><span class="sxs-lookup"><span data-stu-id="912dc-137">Example</span></span>

<span data-ttu-id="912dc-138">Следующий пример создает экземпляр <xref:System.TimeSpan> объекта и пытается отформатировать его <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> с помощью метода, используя неподдерживаемую строку стандартного формата.</span><span class="sxs-lookup"><span data-stu-id="912dc-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="912dc-139">При запуске примера на .NET Framework 3,5 или более ранней версии отображаются следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="912dc-139">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```
12:30:45
```

<span data-ttu-id="912dc-140">При выполнении примера на .NET Framework 4 или более поздней версии это отличает его от выходных данных.</span><span class="sxs-lookup"><span data-stu-id="912dc-140">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```
Invalid Format
```

<span data-ttu-id="912dc-141">Однако, если добавить в каталог примера следующий файл конфигурации, а затем запустить пример на .NET Framework 4 или более поздней версии, то выходные данные идентичны тому, что был создан в примере, когда он выполняется в .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="912dc-141">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="912dc-142">См. также</span><span class="sxs-lookup"><span data-stu-id="912dc-142">See also</span></span>

- [<span data-ttu-id="912dc-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="912dc-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="912dc-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="912dc-144">Configuration File Schema</span></span>](../index.md)
