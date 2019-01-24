---
title: '&lt;EnableAmPmParseAdjustment&gt; элемент'
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97bb5912ec4d384260e3809166efacded8e2b389
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679101"
---
# <a name="ltenableampmparseadjustmentgt-element"></a><span data-ttu-id="286c2-102">&lt;EnableAmPmParseAdjustment&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="286c2-102">&lt;EnableAmPmParseAdjustment&gt; Element</span></span>
<span data-ttu-id="286c2-103">Определяет методы анализа даты и времени использования скорректированной набор правил для анализа строк даты, которые содержат день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="286c2-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="286c2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="286c2-104">\<configuration></span></span>  
 <span data-ttu-id="286c2-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="286c2-105">\<runtime></span></span>  
<span data-ttu-id="286c2-106">\<EnableAmPmParseAdjustment ></span><span class="sxs-lookup"><span data-stu-id="286c2-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="286c2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="286c2-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="286c2-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="286c2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="286c2-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="286c2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="286c2-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="286c2-110">Attributes</span></span>  
  
|<span data-ttu-id="286c2-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="286c2-111">Attribute</span></span>|<span data-ttu-id="286c2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="286c2-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="286c2-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="286c2-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="286c2-114">Разрешение методы анализа даты и времени скорректированной набор правил для анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="286c2-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="286c2-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="286c2-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="286c2-116">Значение</span><span class="sxs-lookup"><span data-stu-id="286c2-116">Value</span></span>|<span data-ttu-id="286c2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="286c2-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="286c2-118">0</span><span class="sxs-lookup"><span data-stu-id="286c2-118">0</span></span>|<span data-ttu-id="286c2-119">Методы анализа даты и времени не используйте скорректированное правил для анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="286c2-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="286c2-120">1</span><span class="sxs-lookup"><span data-stu-id="286c2-120">1</span></span>|<span data-ttu-id="286c2-121">Методы анализа даты и времени скорректированной правила можно использовать для синтаксического анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="286c2-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="286c2-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="286c2-122">Child Elements</span></span>  
 <span data-ttu-id="286c2-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="286c2-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="286c2-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="286c2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="286c2-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="286c2-125">Element</span></span>|<span data-ttu-id="286c2-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="286c2-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="286c2-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="286c2-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="286c2-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="286c2-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="286c2-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="286c2-129">Remarks</span></span>  
 <span data-ttu-id="286c2-130">`<EnableAmPmParseAdjustment>` Элемент управляет как следующие методы проанализировать строку даты, который содержит числовой день и месяц, за которым следует один час и указатель AM/PM (например, «6 4/10 AM»):</span><span class="sxs-lookup"><span data-stu-id="286c2-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="286c2-131">Другие шаблоны не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="286c2-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="286c2-132">`<EnableAmPmParseAdjustment>` Элемент не оказывает влияния на <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, и <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> методы.</span><span class="sxs-lookup"><span data-stu-id="286c2-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="286c2-133">В .NET Core и .NET Native скорректированное правила анализа AM/PM включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="286c2-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="286c2-134">Если синтаксического анализа правило коррекции не включена, первая цифра строка интерпретируется как час 12-часовом формате и учитывается в оставшейся части строки, за исключением указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="286c2-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="286c2-135">Дата и время, возвращаемых методом анализа состоит из текущей даты и часа дня, извлеченных из строки даты.</span><span class="sxs-lookup"><span data-stu-id="286c2-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="286c2-136">Если включен синтаксический анализ правила коррекции, методу анализа интерпретировать день и месяц как относящиеся к текущему году и интерпретировать времени в формате часа 12-часовом формате.</span><span class="sxs-lookup"><span data-stu-id="286c2-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="286c2-137">В следующей таблице показаны различия в <xref:System.DateTime> значения при <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> метод используется для анализа строки ««4/10 6 AM» с `<EnableAmPmParseAdjustment>` элемента `enabled` свойству присвоено значение «0» или «1».</span><span class="sxs-lookup"><span data-stu-id="286c2-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="286c2-138">Предполагается, что сегодняшняя дата 5 января 2017 г. и отображает дату, как если бы он отформатирован с помощью строки формата «G» для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="286c2-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="286c2-139">Имя языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="286c2-139">Culture name</span></span>|<span data-ttu-id="286c2-140">enabled="0"</span><span class="sxs-lookup"><span data-stu-id="286c2-140">enabled="0"</span></span>|<span data-ttu-id="286c2-141">enabled="1"</span><span class="sxs-lookup"><span data-stu-id="286c2-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="286c2-142">en-US</span><span class="sxs-lookup"><span data-stu-id="286c2-142">en-US</span></span>|<span data-ttu-id="286c2-143">1/5/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="286c2-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="286c2-144">4/10/2017 06:00:00: 00</span><span class="sxs-lookup"><span data-stu-id="286c2-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="286c2-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="286c2-145">en-GB</span></span>|<span data-ttu-id="286c2-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="286c2-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="286c2-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="286c2-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="286c2-148">См. также</span><span class="sxs-lookup"><span data-stu-id="286c2-148">See also</span></span>
- [<span data-ttu-id="286c2-149">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="286c2-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [<span data-ttu-id="286c2-150">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="286c2-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
