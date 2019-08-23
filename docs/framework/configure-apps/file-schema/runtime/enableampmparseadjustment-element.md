---
title: Элемент <EnableAmPmParseAdjustment>
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46cf37ee800c05eb7fe12e8491ad3b2130c3a04d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920822"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="34adf-102">\<Элемент > Енаблеампмпарсеаджустмент</span><span class="sxs-lookup"><span data-stu-id="34adf-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="34adf-103">Определяет, используют ли методы синтаксического анализа даты и времени настроенный набор правил для синтаксического анализа строк даты, содержащих день, месяц, час и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="34adf-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="34adf-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="34adf-104">\<configuration></span></span>  
 <span data-ttu-id="34adf-105">\<> среды выполнения</span><span class="sxs-lookup"><span data-stu-id="34adf-105">\<runtime></span></span>  
<span data-ttu-id="34adf-106">\<Енаблеампмпарсеаджустмент ></span><span class="sxs-lookup"><span data-stu-id="34adf-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34adf-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34adf-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34adf-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="34adf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="34adf-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="34adf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34adf-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="34adf-110">Attributes</span></span>  
  
|<span data-ttu-id="34adf-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="34adf-111">Attribute</span></span>|<span data-ttu-id="34adf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="34adf-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="34adf-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="34adf-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="34adf-114">Указывает, используют ли методы синтаксического анализа даты и времени настроенный набор правил для анализа строк даты, содержащих только день, месяц, час и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="34adf-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="34adf-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="34adf-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="34adf-116">Значение</span><span class="sxs-lookup"><span data-stu-id="34adf-116">Value</span></span>|<span data-ttu-id="34adf-117">Описание</span><span class="sxs-lookup"><span data-stu-id="34adf-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="34adf-118">0</span><span class="sxs-lookup"><span data-stu-id="34adf-118">0</span></span>|<span data-ttu-id="34adf-119">Методы синтаксического анализа даты и времени не используют скорректированные правила для анализа строк даты, содержащих только день, месяц, час и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="34adf-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="34adf-120">1</span><span class="sxs-lookup"><span data-stu-id="34adf-120">1</span></span>|<span data-ttu-id="34adf-121">Методы синтаксического анализа даты и времени используют скорректированные правила для анализа строк даты, содержащих только день, месяц, час и обозначение AM/PM.</span><span class="sxs-lookup"><span data-stu-id="34adf-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34adf-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="34adf-122">Child Elements</span></span>  
 <span data-ttu-id="34adf-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="34adf-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34adf-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="34adf-124">Parent Elements</span></span>  
  
|<span data-ttu-id="34adf-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="34adf-125">Element</span></span>|<span data-ttu-id="34adf-126">Описание</span><span class="sxs-lookup"><span data-stu-id="34adf-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34adf-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="34adf-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="34adf-128">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="34adf-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34adf-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="34adf-129">Remarks</span></span>  
 <span data-ttu-id="34adf-130">`<EnableAmPmParseAdjustment>` Элемент определяет, как следующие методы анализируют строку даты, которая содержит числовой день и месяц, за которыми следует час и обозначение AM/PM (например, "4/10 6 AM"):</span><span class="sxs-lookup"><span data-stu-id="34adf-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="34adf-131">Другие шаблоны не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="34adf-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="34adf-132"><xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType> <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>Элемент не влияет на методы,, и<xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> . `<EnableAmPmParseAdjustment>`</span><span class="sxs-lookup"><span data-stu-id="34adf-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="34adf-133">В .NET Core и .NET Native настроенные правила анализа AM/PM включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="34adf-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="34adf-134">Если правило коррекции синтаксического анализа не включено, первая цифра строки интерпретируется как час 12-часового времени, а оставшаяся часть строки, за исключением обозначения AM/PM, игнорируется.</span><span class="sxs-lookup"><span data-stu-id="34adf-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="34adf-135">Дата и время, возвращаемые методом анализа, состоят из текущей даты и часа дня, извлеченных из строки даты.</span><span class="sxs-lookup"><span data-stu-id="34adf-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="34adf-136">Если правило коррекции синтаксического анализа включено, метод синтаксического анализа интерпретирует день и месяц как принадлежащий текущему году и интерпретирует время как час 12-часового времени.</span><span class="sxs-lookup"><span data-stu-id="34adf-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="34adf-137">В следующей таблице <xref:System.DateTime> показано различие в значении, <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> когда метод используется для синтаксического анализа строки "" `<EnableAmPmParseAdjustment>` 4/10 6 AM `enabled` "со свойством элемента, имеющим значение" 0 "или" 1 ".</span><span class="sxs-lookup"><span data-stu-id="34adf-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="34adf-138">Предполагается, что сегодняшняя дата — 5 января 2017, а дата отображается так, как если бы она была отформатирована с использованием строки формата "G" указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="34adf-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="34adf-139">Имя языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="34adf-139">Culture name</span></span>|<span data-ttu-id="34adf-140">Enabled = "0"</span><span class="sxs-lookup"><span data-stu-id="34adf-140">enabled="0"</span></span>|<span data-ttu-id="34adf-141">enabled="1"</span><span class="sxs-lookup"><span data-stu-id="34adf-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="34adf-142">en-US</span><span class="sxs-lookup"><span data-stu-id="34adf-142">en-US</span></span>|<span data-ttu-id="34adf-143">1/5/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="34adf-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="34adf-144">4/10/2017 6:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="34adf-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="34adf-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="34adf-145">en-GB</span></span>|<span data-ttu-id="34adf-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="34adf-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="34adf-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="34adf-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34adf-148">См. также</span><span class="sxs-lookup"><span data-stu-id="34adf-148">See also</span></span>

- [<span data-ttu-id="34adf-149">\<Элемент > среды выполнения</span><span class="sxs-lookup"><span data-stu-id="34adf-149">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="34adf-150">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="34adf-150">\<configuration> Element</span></span>](../configuration-element.md)
