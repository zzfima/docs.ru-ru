---
title: '&lt;EnableAmPmParseAdjustment&gt; элемент'
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b17f521be31fa4082d9418c7dad734e37994bbb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752823"
---
# <a name="ltenableampmparseadjustmentgt-element"></a><span data-ttu-id="9b603-102">&lt;EnableAmPmParseAdjustment&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="9b603-102">&lt;EnableAmPmParseAdjustment&gt; Element</span></span>
<span data-ttu-id="9b603-103">Определяет дату и время методов синтаксического анализа использования скорректированное набор правил, выполнить синтаксический анализ строк даты, которые содержат день, месяц, часов и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="9b603-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="9b603-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9b603-104">\<configuration></span></span>  
 <span data-ttu-id="9b603-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="9b603-105">\<runtime></span></span>  
<span data-ttu-id="9b603-106">\<EnableAmPmParseAdjustment ></span><span class="sxs-lookup"><span data-stu-id="9b603-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b603-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b603-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b603-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9b603-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9b603-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9b603-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b603-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b603-110">Attributes</span></span>  
  
|<span data-ttu-id="9b603-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9b603-111">Attribute</span></span>|<span data-ttu-id="9b603-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9b603-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9b603-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9b603-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9b603-114">Указывает дату и время методов синтаксического анализа использования скорректированное набор правил, выполнить синтаксический анализ строк даты, которые содержат только день, месяц, часов и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="9b603-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="9b603-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="9b603-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9b603-116">Значение</span><span class="sxs-lookup"><span data-stu-id="9b603-116">Value</span></span>|<span data-ttu-id="9b603-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9b603-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9b603-118">0</span><span class="sxs-lookup"><span data-stu-id="9b603-118">0</span></span>|<span data-ttu-id="9b603-119">Дата и время методов синтаксического анализа не использовать скорректированное правила для разбора строки даты, которые содержат только день, месяц, часов и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="9b603-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="9b603-120">1</span><span class="sxs-lookup"><span data-stu-id="9b603-120">1</span></span>|<span data-ttu-id="9b603-121">Дата и время методов синтаксического анализа скорректированное правила можно использовать для синтаксического анализа строки даты, которые содержат только день, месяц, часов и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="9b603-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b603-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9b603-122">Child Elements</span></span>  
 <span data-ttu-id="9b603-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9b603-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b603-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9b603-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9b603-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b603-125">Element</span></span>|<span data-ttu-id="9b603-126">Описание</span><span class="sxs-lookup"><span data-stu-id="9b603-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9b603-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9b603-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9b603-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="9b603-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b603-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b603-129">Remarks</span></span>  
 <span data-ttu-id="9b603-130">`<EnableAmPmParseAdjustment>` Элемент управляет как следующие методы синтаксический анализ строки даты, содержащий числовое значение дня и месяца, за которым следует один час и обозначение AM/PM (например, «4/10 6 AM»):</span><span class="sxs-lookup"><span data-stu-id="9b603-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="9b603-131">Другие шаблоны не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="9b603-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="9b603-132">`<EnableAmPmParseAdjustment>` Элемент не оказывает влияния на <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, и <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> методы.</span><span class="sxs-lookup"><span data-stu-id="9b603-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9b603-133">В .NET Core и .NET Native скорректированное правила синтаксического разбора AM/PM включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9b603-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="9b603-134">Если правила коррекции синтаксического анализа не включен, первая цифра строки интерпретируется как час в 12-часовом формате и остальная часть строки, за исключением обозначение AM/PM игнорируется.</span><span class="sxs-lookup"><span data-stu-id="9b603-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="9b603-135">Дата и время возврата с помощью метода анализа состоит из текущей даты и времени извлекается из строки даты.</span><span class="sxs-lookup"><span data-stu-id="9b603-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="9b603-136">При включении синтаксического анализа правила коррекции анализ метод интерпретировать день и месяц как принадлежащие текущий год и интерпретировать время как час в 12-часовом формате.</span><span class="sxs-lookup"><span data-stu-id="9b603-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="9b603-137">В следующей таблице показаны различия в <xref:System.DateTime> значения при <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> метод используется для анализа строки ««4/10 6 AM» с `<EnableAmPmParseAdjustment>` элемента `enabled` свойством, имеющим значение «0» или «1».</span><span class="sxs-lookup"><span data-stu-id="9b603-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="9b603-138">Он предполагается, что сегодняшняя дата — 5 января 2017 г. и отображает дату, как если бы он отформатирован с помощью строки формата «G» для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="9b603-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="9b603-139">Имя языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="9b603-139">Culture name</span></span>|<span data-ttu-id="9b603-140">Включить = «0»</span><span class="sxs-lookup"><span data-stu-id="9b603-140">enabled="0"</span></span>|<span data-ttu-id="9b603-141">Включить = «1»</span><span class="sxs-lookup"><span data-stu-id="9b603-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="9b603-142">ru-RU</span><span class="sxs-lookup"><span data-stu-id="9b603-142">en-US</span></span>|<span data-ttu-id="9b603-143">1/5/2017 Г 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="9b603-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="9b603-144">4/10/2017 Г. 6:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="9b603-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="9b603-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="9b603-145">en-GB</span></span>|<span data-ttu-id="9b603-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="9b603-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="9b603-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="9b603-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b603-148">См. также</span><span class="sxs-lookup"><span data-stu-id="9b603-148">See Also</span></span>  
 [<span data-ttu-id="9b603-149">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="9b603-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
 [<span data-ttu-id="9b603-150">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="9b603-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
