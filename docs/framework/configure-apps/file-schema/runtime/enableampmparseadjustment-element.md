---
title: Элемент <EnableAmPmParseAdjustment>
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3316184aaa624fffdd18f472a7f3a709b42045a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269215"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="bb0f6-102">\<EnableAmPmParseAdjustment > элемент</span><span class="sxs-lookup"><span data-stu-id="bb0f6-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="bb0f6-103">Определяет методы анализа даты и времени использования скорректированной набор правил для анализа строк даты, которые содержат день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="bb0f6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bb0f6-104">\<configuration></span></span>  
 <span data-ttu-id="bb0f6-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="bb0f6-105">\<runtime></span></span>  
<span data-ttu-id="bb0f6-106">\<EnableAmPmParseAdjustment ></span><span class="sxs-lookup"><span data-stu-id="bb0f6-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb0f6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb0f6-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb0f6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bb0f6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bb0f6-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb0f6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bb0f6-110">Attributes</span></span>  
  
|<span data-ttu-id="bb0f6-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bb0f6-111">Attribute</span></span>|<span data-ttu-id="bb0f6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bb0f6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="bb0f6-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="bb0f6-114">Разрешение методы анализа даты и времени скорректированной набор правил для анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="bb0f6-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="bb0f6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="bb0f6-116">Значение</span><span class="sxs-lookup"><span data-stu-id="bb0f6-116">Value</span></span>|<span data-ttu-id="bb0f6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="bb0f6-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bb0f6-118">0</span><span class="sxs-lookup"><span data-stu-id="bb0f6-118">0</span></span>|<span data-ttu-id="bb0f6-119">Методы анализа даты и времени не используйте скорректированное правил для анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="bb0f6-120">1</span><span class="sxs-lookup"><span data-stu-id="bb0f6-120">1</span></span>|<span data-ttu-id="bb0f6-121">Методы анализа даты и времени скорректированной правила можно использовать для синтаксического анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb0f6-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bb0f6-122">Child Elements</span></span>  
 <span data-ttu-id="bb0f6-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb0f6-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bb0f6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bb0f6-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb0f6-125">Element</span></span>|<span data-ttu-id="bb0f6-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="bb0f6-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bb0f6-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bb0f6-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb0f6-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="bb0f6-129">Remarks</span></span>  
 <span data-ttu-id="bb0f6-130">`<EnableAmPmParseAdjustment>` Элемент управляет как следующие методы проанализировать строку даты, который содержит числовой день и месяц, за которым следует один час и указатель AM/PM (например, «6 4/10 AM»):</span><span class="sxs-lookup"><span data-stu-id="bb0f6-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="bb0f6-131">Другие шаблоны не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="bb0f6-132">`<EnableAmPmParseAdjustment>` Элемент не оказывает влияния на <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, и <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> методы.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bb0f6-133">В .NET Core и .NET Native скорректированное правила анализа AM/PM включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="bb0f6-134">Если синтаксического анализа правило коррекции не включена, первая цифра строка интерпретируется как час 12-часовом формате и учитывается в оставшейся части строки, за исключением указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="bb0f6-135">Дата и время, возвращаемых методом анализа состоит из текущей даты и часа дня, извлеченных из строки даты.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="bb0f6-136">Если включен синтаксический анализ правила коррекции, методу анализа интерпретировать день и месяц как относящиеся к текущему году и интерпретировать времени в формате часа 12-часовом формате.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="bb0f6-137">В следующей таблице показаны различия в <xref:System.DateTime> значения при <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> метод используется для анализа строки ««4/10 6 AM» с `<EnableAmPmParseAdjustment>` элемента `enabled` свойству присвоено значение «0» или «1».</span><span class="sxs-lookup"><span data-stu-id="bb0f6-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="bb0f6-138">Предполагается, что сегодняшняя дата 5 января 2017 г. и отображает дату, как если бы он отформатирован с помощью строки формата «G» для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="bb0f6-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="bb0f6-139">Имя языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="bb0f6-139">Culture name</span></span>|<span data-ttu-id="bb0f6-140">enabled="0"</span><span class="sxs-lookup"><span data-stu-id="bb0f6-140">enabled="0"</span></span>|<span data-ttu-id="bb0f6-141">enabled="1"</span><span class="sxs-lookup"><span data-stu-id="bb0f6-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="bb0f6-142">en-US</span><span class="sxs-lookup"><span data-stu-id="bb0f6-142">en-US</span></span>|<span data-ttu-id="bb0f6-143">1/5/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="bb0f6-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="bb0f6-144">4/10/2017 06:00:00: 00</span><span class="sxs-lookup"><span data-stu-id="bb0f6-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="bb0f6-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="bb0f6-145">en-GB</span></span>|<span data-ttu-id="bb0f6-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="bb0f6-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="bb0f6-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="bb0f6-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb0f6-148">См. также</span><span class="sxs-lookup"><span data-stu-id="bb0f6-148">See also</span></span>
- [<span data-ttu-id="bb0f6-149">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="bb0f6-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [<span data-ttu-id="bb0f6-150">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="bb0f6-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
