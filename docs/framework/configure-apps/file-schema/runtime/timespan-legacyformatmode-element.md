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
ms.openlocfilehash: c835e1bcef7bbfdc990c8db177eafed4ec6bb30c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115214"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="6769e-102">\<TimeSpan_LegacyFormatMode > элемент</span><span class="sxs-lookup"><span data-stu-id="6769e-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="6769e-103">Определяет, сохраняет ли среда выполнения устаревшее поведение в операциях форматирования с <xref:System.TimeSpan?displayProperty=nameWithType> значениями.</span><span class="sxs-lookup"><span data-stu-id="6769e-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

<span data-ttu-id="6769e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6769e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6769e-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="6769e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="6769e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<TimeSpan_LegacyFormatMode >**</span><span class="sxs-lookup"><span data-stu-id="6769e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="6769e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6769e-107">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6769e-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6769e-108">Attributes and Elements</span></span>

<span data-ttu-id="6769e-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6769e-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6769e-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6769e-110">Attributes</span></span>

|<span data-ttu-id="6769e-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6769e-111">Attribute</span></span>|<span data-ttu-id="6769e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6769e-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="6769e-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6769e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6769e-114">Указывает, использует ли среда выполнения устаревшее поведение форматирования с <xref:System.TimeSpan?displayProperty=nameWithType> значениями.</span><span class="sxs-lookup"><span data-stu-id="6769e-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="6769e-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="6769e-115">enabled Attribute</span></span>

|<span data-ttu-id="6769e-116">значения</span><span class="sxs-lookup"><span data-stu-id="6769e-116">Value</span></span>|<span data-ttu-id="6769e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6769e-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="6769e-118">Среда выполнения не восстанавливает устаревшее поведение форматирования.</span><span class="sxs-lookup"><span data-stu-id="6769e-118">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="6769e-119">Среда выполнения восстанавливает устаревшее поведение форматирования.</span><span class="sxs-lookup"><span data-stu-id="6769e-119">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6769e-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6769e-120">Child Elements</span></span>

<span data-ttu-id="6769e-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6769e-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6769e-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6769e-122">Parent Elements</span></span>

|<span data-ttu-id="6769e-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="6769e-123">Element</span></span>|<span data-ttu-id="6769e-124">Описание</span><span class="sxs-lookup"><span data-stu-id="6769e-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="6769e-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6769e-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="6769e-126">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6769e-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6769e-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="6769e-127">Remarks</span></span>

<span data-ttu-id="6769e-128">Начиная с .NET Framework 4 Структура <xref:System.TimeSpan?displayProperty=nameWithType> реализует интерфейс <xref:System.IFormattable> и поддерживает операции форматирования со стандартными и пользовательскими строками формата.</span><span class="sxs-lookup"><span data-stu-id="6769e-128">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="6769e-129">Если метод синтаксического анализа встречает неподдерживаемый описатель формата или строку формата, он выдает исключение <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="6769e-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="6769e-130">В предыдущих версиях .NET Framework структура <xref:System.TimeSpan> не реализовала <xref:System.IFormattable> и не поддерживала строки формата.</span><span class="sxs-lookup"><span data-stu-id="6769e-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="6769e-131">Однако многие разработчики ошибочно предполагали, что <xref:System.TimeSpan> поддерживали набор строк формата и использовали их в [операциях составного форматирования](../../../../standard/base-types/composite-formatting.md) с такими методами, как <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6769e-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6769e-132">Обычно, если тип реализует <xref:System.IFormattable> и поддерживает строки формата, вызовы методов форматирования с неподдерживаемыми строками формата обычно создают <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="6769e-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="6769e-133">Однако поскольку <xref:System.TimeSpan> не реализовал <xref:System.IFormattable>, среда выполнения игнорирует строку формата и вызывает метод <xref:System.TimeSpan.ToString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6769e-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6769e-134">Это означает, что, хотя строки формата не оказывают влияния на операцию форматирования, их присутствие не привело к <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="6769e-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="6769e-135">В случаях, когда устаревший код передает метод составного форматирования и недопустимую строку формата, и этот код не может быть перекомпилирован, можно использовать элемент `<TimeSpan_LegacyFormatMode>` для восстановления прежнего поведения <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="6769e-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="6769e-136">Если для атрибута `enabled` этого элемента задано значение `true`, метод составного форматирования приводит к вызову <xref:System.TimeSpan.ToString?displayProperty=nameWithType>, а не <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, а <xref:System.FormatException> не создается.</span><span class="sxs-lookup"><span data-stu-id="6769e-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="6769e-137">Пример</span><span class="sxs-lookup"><span data-stu-id="6769e-137">Example</span></span>

<span data-ttu-id="6769e-138">Следующий пример создает экземпляр объекта <xref:System.TimeSpan> и пытается отформатировать его с помощью метода <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType>, используя неподдерживаемую строку стандартного формата.</span><span class="sxs-lookup"><span data-stu-id="6769e-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="6769e-139">При запуске примера на .NET Framework 3,5 или более ранней версии отображаются следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="6769e-139">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```
12:30:45
```

<span data-ttu-id="6769e-140">При выполнении примера на .NET Framework 4 или более поздней версии это отличает его от выходных данных.</span><span class="sxs-lookup"><span data-stu-id="6769e-140">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```
Invalid Format
```

<span data-ttu-id="6769e-141">Однако, если добавить в каталог примера следующий файл конфигурации, а затем запустить пример на .NET Framework 4 или более поздней версии, то выходные данные идентичны тому, что был создан в примере, когда он выполняется в .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="6769e-141">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="6769e-142">См. также</span><span class="sxs-lookup"><span data-stu-id="6769e-142">See also</span></span>

- [<span data-ttu-id="6769e-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="6769e-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6769e-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="6769e-144">Configuration File Schema</span></span>](../index.md)
