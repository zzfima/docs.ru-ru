---
title: <EnableAmPmParseAdjustment> Элемент
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d1a14199debbb90827c1ea95347d485a636329
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222514"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="4f142-102">\<EnableAmPmParseAdjustment > элемент</span><span class="sxs-lookup"><span data-stu-id="4f142-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="4f142-103">Определяет методы анализа даты и времени использования скорректированной набор правил для анализа строк даты, которые содержат день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="4f142-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="4f142-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4f142-104">\<configuration></span></span>  
 <span data-ttu-id="4f142-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="4f142-105">\<runtime></span></span>  
<span data-ttu-id="4f142-106">\<EnableAmPmParseAdjustment ></span><span class="sxs-lookup"><span data-stu-id="4f142-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f142-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f142-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f142-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4f142-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4f142-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4f142-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f142-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4f142-110">Attributes</span></span>  
  
|<span data-ttu-id="4f142-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4f142-111">Attribute</span></span>|<span data-ttu-id="4f142-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4f142-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4f142-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4f142-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4f142-114">Разрешение методы анализа даты и времени скорректированной набор правил для анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="4f142-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="4f142-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="4f142-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4f142-116">Значение</span><span class="sxs-lookup"><span data-stu-id="4f142-116">Value</span></span>|<span data-ttu-id="4f142-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4f142-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4f142-118">0</span><span class="sxs-lookup"><span data-stu-id="4f142-118">0</span></span>|<span data-ttu-id="4f142-119">Методы анализа даты и времени не используйте скорректированное правил для анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="4f142-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="4f142-120">1</span><span class="sxs-lookup"><span data-stu-id="4f142-120">1</span></span>|<span data-ttu-id="4f142-121">Методы анализа даты и времени скорректированной правила можно использовать для синтаксического анализа строк даты, содержащих только день, месяц, час и указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="4f142-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f142-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4f142-122">Child Elements</span></span>  
 <span data-ttu-id="4f142-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4f142-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f142-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4f142-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4f142-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="4f142-125">Element</span></span>|<span data-ttu-id="4f142-126">Описание</span><span class="sxs-lookup"><span data-stu-id="4f142-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4f142-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f142-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4f142-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4f142-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f142-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f142-129">Remarks</span></span>  
 <span data-ttu-id="4f142-130">`<EnableAmPmParseAdjustment>` Элемент управляет как следующие методы проанализировать строку даты, который содержит числовой день и месяц, за которым следует один час и указатель AM/PM (например, «6 4/10 AM»):</span><span class="sxs-lookup"><span data-stu-id="4f142-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="4f142-131">Другие шаблоны не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="4f142-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="4f142-132">`<EnableAmPmParseAdjustment>` Элемент не оказывает влияния на <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, и <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> методы.</span><span class="sxs-lookup"><span data-stu-id="4f142-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4f142-133">В .NET Core и .NET Native скорректированное правила анализа AM/PM включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4f142-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="4f142-134">Если синтаксического анализа правило коррекции не включена, первая цифра строка интерпретируется как час 12-часовом формате и учитывается в оставшейся части строки, за исключением указатель AM/PM.</span><span class="sxs-lookup"><span data-stu-id="4f142-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="4f142-135">Дата и время, возвращаемых методом анализа состоит из текущей даты и часа дня, извлеченных из строки даты.</span><span class="sxs-lookup"><span data-stu-id="4f142-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="4f142-136">Если включен синтаксический анализ правила коррекции, методу анализа интерпретировать день и месяц как относящиеся к текущему году и интерпретировать времени в формате часа 12-часовом формате.</span><span class="sxs-lookup"><span data-stu-id="4f142-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="4f142-137">В следующей таблице показаны различия в <xref:System.DateTime> значения при <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> метод используется для анализа строки ««4/10 6 AM» с `<EnableAmPmParseAdjustment>` элемента `enabled` свойству присвоено значение «0» или «1».</span><span class="sxs-lookup"><span data-stu-id="4f142-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="4f142-138">Предполагается, что сегодняшняя дата 5 января 2017 г. и отображает дату, как если бы он отформатирован с помощью строки формата «G» для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="4f142-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="4f142-139">Имя языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="4f142-139">Culture name</span></span>|<span data-ttu-id="4f142-140">enabled="0"</span><span class="sxs-lookup"><span data-stu-id="4f142-140">enabled="0"</span></span>|<span data-ttu-id="4f142-141">enabled="1"</span><span class="sxs-lookup"><span data-stu-id="4f142-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="4f142-142">en-US</span><span class="sxs-lookup"><span data-stu-id="4f142-142">en-US</span></span>|<span data-ttu-id="4f142-143">1/5/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="4f142-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="4f142-144">4/10/2017 06:00:00: 00</span><span class="sxs-lookup"><span data-stu-id="4f142-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="4f142-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="4f142-145">en-GB</span></span>|<span data-ttu-id="4f142-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="4f142-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="4f142-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="4f142-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f142-148">См. также</span><span class="sxs-lookup"><span data-stu-id="4f142-148">See also</span></span>

- [<span data-ttu-id="4f142-149">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="4f142-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [<span data-ttu-id="4f142-150">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="4f142-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
