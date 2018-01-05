---
title: "Синтаксис DateTime XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3010d3123e78a5e292c5ac78ef4894962fb8f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="datetime-xaml-syntax"></a><span data-ttu-id="dae88-102">Синтаксис DateTime XAML</span><span class="sxs-lookup"><span data-stu-id="dae88-102">DateTime XAML Syntax</span></span>
<span data-ttu-id="dae88-103">Некоторые элементы управления, такие как <xref:System.Windows.Controls.Calendar> и <xref:System.Windows.Controls.DatePicker>, имеют свойства, использующие <xref:System.DateTime> типа.</span><span class="sxs-lookup"><span data-stu-id="dae88-103">Some controls, such as <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>, have properties that use the <xref:System.DateTime> type.</span></span> <span data-ttu-id="dae88-104">Несмотря на то что начальные дата и время для этих элементов управления обычно указываются в коде программной части во время выполнения, их можно указать в коде XAML.</span><span class="sxs-lookup"><span data-stu-id="dae88-104">Although you typically specify an initial date or time for these controls in the code-behind at run time, you can specify an initial date or time in XAML.</span></span> <span data-ttu-id="dae88-105">Средство синтаксического анализа WPF XAML обрабатывает анализ <xref:System.DateTime> значения с помощью встроенных текстового синтаксиса XAML.</span><span class="sxs-lookup"><span data-stu-id="dae88-105">The WPF XAML parser handles parsing of <xref:System.DateTime> values using a built-in XAML text syntax.</span></span> <span data-ttu-id="dae88-106">В этом разделе описаны особенности <xref:System.DateTime> текстового синтаксиса XAML.</span><span class="sxs-lookup"><span data-stu-id="dae88-106">This topic describes the specifics of the <xref:System.DateTime> XAML text syntax.</span></span>  
  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a><span data-ttu-id="dae88-107">Когда требуется использовать синтаксис DateTime XAML</span><span class="sxs-lookup"><span data-stu-id="dae88-107">When To Use DateTime XAML Syntax</span></span>  
 <span data-ttu-id="dae88-108">Задание дат в XAML не всегда обязательно, а иногда даже может быть нежелательно.</span><span class="sxs-lookup"><span data-stu-id="dae88-108">Setting dates in XAML is not always necessary and may not even be desirable.</span></span> <span data-ttu-id="dae88-109">Например, можно использовать <xref:System.DateTime.Now%2A?displayProperty=nameWithType> инициализацию даты во время выполнения, или можно сделать все корректировки дат календаря в кода на основе ввода пользователя.</span><span class="sxs-lookup"><span data-stu-id="dae88-109">For example, you could use the <xref:System.DateTime.Now%2A?displayProperty=nameWithType> property to initialize a date at run time, or you could do all your date adjustments for a calendar in the code-behind based on user input.</span></span> <span data-ttu-id="dae88-110">Однако существуют сценарии, где можно жестко закодировать дат в <xref:System.Windows.Controls.Calendar> и <xref:System.Windows.Controls.DatePicker> в шаблоне элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dae88-110">However, there are scenarios where you may want to hard-code dates into a <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker> in a control template.</span></span> <span data-ttu-id="dae88-111"><xref:System.DateTime> Синтаксиса XAML должен использоваться в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="dae88-111">The <xref:System.DateTime> XAML syntax must be used for these scenarios.</span></span>  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a><span data-ttu-id="dae88-112">Синтаксис DateTime XAML является собственным поведением</span><span class="sxs-lookup"><span data-stu-id="dae88-112">DateTime XAML Syntax is a Native Behavior</span></span>  
 <span data-ttu-id="dae88-113"><xref:System.DateTime>— Это класс, который определен в библиотеках базовых классов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="dae88-113"><xref:System.DateTime> is a class that is defined in the base class libraries of the CLR.</span></span> <span data-ttu-id="dae88-114">Из-за связи библиотеки базовых классов с остальной части среды CLR, не удалось применить <xref:System.ComponentModel.TypeConverterAttribute> класс и использовать преобразователь типов для обработки строк из XAML и преобразовать их в <xref:System.DateTime> в объектной модели время выполнения.</span><span class="sxs-lookup"><span data-stu-id="dae88-114">Because of how the base class libraries relate to the rest of the CLR, it is not possible to apply <xref:System.ComponentModel.TypeConverterAttribute> to the class and use a type converter to process strings from XAML and convert them to <xref:System.DateTime> in the run time object model.</span></span> <span data-ttu-id="dae88-115">Нет класса `DateTimeConverter`, предоставляющего поведение преобразования: поведение преобразования, описанное в этом разделе, является собственным для средства синтаксического анализа XAML WPF.</span><span class="sxs-lookup"><span data-stu-id="dae88-115">There is no `DateTimeConverter` class that provides the conversion behavior; the conversion behavior described in this topic is native to the WPF XAML parser.</span></span>  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a><span data-ttu-id="dae88-116">Строки формата для синтаксиса DateTime XAML</span><span class="sxs-lookup"><span data-stu-id="dae88-116">Format Strings for DateTime XAML Syntax</span></span>  
 <span data-ttu-id="dae88-117">Можно указать формат <xref:System.DateTime> со строкой формата.</span><span class="sxs-lookup"><span data-stu-id="dae88-117">You can specify the format of a <xref:System.DateTime> with a format string.</span></span> <span data-ttu-id="dae88-118">Строки формата формализуют синтаксис текста, который может использоваться для создания значения.</span><span class="sxs-lookup"><span data-stu-id="dae88-118">Format strings formalize the text syntax that can be used to create a value.</span></span> <span data-ttu-id="dae88-119"><xref:System.DateTime>значения для существующих элементов управления WPF обычно только использование компонентов даты <xref:System.DateTime> и не компоненты времени.</span><span class="sxs-lookup"><span data-stu-id="dae88-119"><xref:System.DateTime> values for the existing WPF controls generally only use the date components of <xref:System.DateTime> and not the time components.</span></span>  
  
 <span data-ttu-id="dae88-120">При указании <xref:System.DateTime> в XAML, можно использовать любой из строк формата попеременно.</span><span class="sxs-lookup"><span data-stu-id="dae88-120">When specifying a <xref:System.DateTime> in XAML, you can use any of the format strings interchangeably.</span></span>  
  
 <span data-ttu-id="dae88-121">Можно также использовать форматы и строки формата, которые не рассматриваются в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="dae88-121">You can also use formats and format strings that are not specifically shown in this topic.</span></span> <span data-ttu-id="dae88-122">С технической точки зрения XAML для любого <xref:System.DateTime> значение, которое указывается, а затем анализируется средством синтаксического анализа WPF XAML использует внутренний вызов <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, поэтому можно использовать любую строку, принято <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> для своих входных данных.</span><span class="sxs-lookup"><span data-stu-id="dae88-122">Technically, the XAML for any <xref:System.DateTime> value that is specified and then parsed by the WPF XAML parser uses an internal  call to <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, therefore you could use any string accepted by <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> for your XAML input.</span></span> <span data-ttu-id="dae88-123">Дополнительные сведения см. в разделе <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dae88-123">For more information, see <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dae88-124">Всегда использует синтаксис DateTime XAML `en-us` как <xref:System.Globalization.CultureInfo> для его собственного преобразования.</span><span class="sxs-lookup"><span data-stu-id="dae88-124">The DateTime XAML syntax always uses `en-us` as the <xref:System.Globalization.CultureInfo> for its native conversion.</span></span> <span data-ttu-id="dae88-125">Это не зависит от <xref:System.Windows.FrameworkElement.Language%2A> значение или `xml:lang` значение в XAML-ФАЙЛЕ, так как преобразования типов на уровне атрибута XAML работает без этого контекста.</span><span class="sxs-lookup"><span data-stu-id="dae88-125">This is not influenced by <xref:System.Windows.FrameworkElement.Language%2A> value or `xml:lang` value in the XAML, because XAML attribute-level type conversion acts without that context.</span></span> <span data-ttu-id="dae88-126">Не пытайтесь выполнять интерполяцию показанных здесь строк формата из-за различий региональных параметров, таких как порядок отображения дня и месяца.</span><span class="sxs-lookup"><span data-stu-id="dae88-126">Do not attempt to interpolate the format strings shown here due to cultural variations, such as the order in which day and month appear.</span></span> <span data-ttu-id="dae88-127">Показанные здесь строки формата — это именно те строки формата, которые используются при синтаксическом анализе XAML независимо от других параметров языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="dae88-127">The format strings shown here are the exact format strings used when parsing the XAML regardless of other culture settings.</span></span>  
  
 <span data-ttu-id="dae88-128">В следующих разделах описаны некоторые общие <xref:System.DateTime> строки формата.</span><span class="sxs-lookup"><span data-stu-id="dae88-128">The following sections describe some of the common <xref:System.DateTime> format strings.</span></span>  
  
### <a name="short-date-pattern-d"></a><span data-ttu-id="dae88-129">Шаблон краткого формата даты (d)</span><span class="sxs-lookup"><span data-stu-id="dae88-129">Short Date Pattern ("d")</span></span>  
 <span data-ttu-id="dae88-130">Ниже приведен краткий формат даты для <xref:System.DateTime> в XAML:</span><span class="sxs-lookup"><span data-stu-id="dae88-130">The following shows the short date format for a <xref:System.DateTime> in XAML:</span></span>  
  
 `M/d/YYYY`  
  
 <span data-ttu-id="dae88-131">Это самая простая форма, определяющая все необходимые сведения для типичного использования элементами управления WPF. На нее не влияют случайные смещения часового пояса (по сравнению с компонентом времени), и поэтому она предпочтительнее других форматов.</span><span class="sxs-lookup"><span data-stu-id="dae88-131">This is the simplest form that specifies all necessary information for typical usages by WPF controls, and cannot be influenced by accidental time zone offsets versus a time component, and is therefore recommended over the other formats.</span></span>  
  
 <span data-ttu-id="dae88-132">Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку.</span><span class="sxs-lookup"><span data-stu-id="dae88-132">For example, to specify the date of June 1, 2010, use the following string:</span></span>  
  
 `3/1/2010`  
  
 <span data-ttu-id="dae88-133">Дополнительные сведения см. в разделе <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dae88-133">For more information, see <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="sortable-datetime-pattern-s"></a><span data-ttu-id="dae88-134">Сортируемый шаблон даты и времени (s)</span><span class="sxs-lookup"><span data-stu-id="dae88-134">Sortable DateTime Pattern ("s")</span></span>  
 <span data-ttu-id="dae88-135">В следующем примере показаны сортируемого <xref:System.DateTime> шаблон в XAML:</span><span class="sxs-lookup"><span data-stu-id="dae88-135">The following shows the sortable <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 <span data-ttu-id="dae88-136">Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку (все компоненты времени вводятся как 0).</span><span class="sxs-lookup"><span data-stu-id="dae88-136">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a><span data-ttu-id="dae88-137">Шаблон RFC1123 (r)</span><span class="sxs-lookup"><span data-stu-id="dae88-137">RFC1123 Pattern ("r")</span></span>  
 <span data-ttu-id="dae88-138">Шаблон RFC1123 удобен, поскольку он может быть строкой ввода из других генераторов данных, также использующих шаблон RFC1123, в ситуациях инвариантных значений языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="dae88-138">The RFC1123 pattern is useful because it could be a string input from other date generators that also use the RFC1123 pattern for culture invariant reasons.</span></span> <span data-ttu-id="dae88-139">В следующем примере показаны RFC1123 <xref:System.DateTime> шаблон в XAML:</span><span class="sxs-lookup"><span data-stu-id="dae88-139">The following shows the RFC1123 <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 <span data-ttu-id="dae88-140">Например, чтобы указать дату 1 июня 2010 г., используйте следующую строку (все компоненты времени вводятся как 0).</span><span class="sxs-lookup"><span data-stu-id="dae88-140">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a><span data-ttu-id="dae88-141">Другие форматы и шаблоны</span><span class="sxs-lookup"><span data-stu-id="dae88-141">Other Formats and Patterns</span></span>  
 <span data-ttu-id="dae88-142">Как уже говорилось ранее, <xref:System.DateTime> в XAML может быть указан как любая строка, которая является допустимым как входные для <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dae88-142">As stated previously, a <xref:System.DateTime> in XAML can be specified as any string that is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="dae88-143">Сюда входят другие форматы, документально оформленными принципами (например <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) и форматы, которые не формализованный как определенный <xref:System.Globalization.DateTimeFormatInfo> формы.</span><span class="sxs-lookup"><span data-stu-id="dae88-143">This includes other formalized formats (for example <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), and formats that are not formalized as a particular <xref:System.Globalization.DateTimeFormatInfo> form.</span></span> <span data-ttu-id="dae88-144">Например, форма `YYYY/mm/dd` приемлем как входные для <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dae88-144">For example, the form `YYYY/mm/dd` is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="dae88-145">Этот раздел не является попыткой описать все возможные форматы: вместо этого рекомендуется использование шаблона короткого формата даты.</span><span class="sxs-lookup"><span data-stu-id="dae88-145">This topic does not attempt to describe all possible formats that work, and instead recommends the short date pattern as a standard practice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae88-146">См. также</span><span class="sxs-lookup"><span data-stu-id="dae88-146">See Also</span></span>  
 [<span data-ttu-id="dae88-147">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="dae88-147">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
