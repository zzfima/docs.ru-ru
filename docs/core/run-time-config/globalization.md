---
title: Параметры конфигурации глобализации
description: Вы можете узнать о параметрах времени выполнения, настраивающих аспекты глобализации для приложения .NET Core, например способа анализа дат на японском языке.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 3764d0eb714c094b44ae843a1e626073ff8d82e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733451"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="b967a-103">Параметры конфигурации времени выполнения для глобализации</span><span class="sxs-lookup"><span data-stu-id="b967a-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="b967a-104">Invariant mode (Инвариантный режим)</span><span class="sxs-lookup"><span data-stu-id="b967a-104">Invariant mode</span></span>

- <span data-ttu-id="b967a-105">Определяет, выполняется ли приложение .NET Core в инвариантном режиме глобализации без доступа к данным и поведению, зависящим от языка и региональных параметров, и имеет ли оно доступ к данным языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="b967a-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="b967a-106">По умолчанию: выполнение приложения с доступом к данным языка и региональных параметров (`false`).</span><span class="sxs-lookup"><span data-stu-id="b967a-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="b967a-107">Дополнительные сведения см. в статье [Инвариантный режим глобализации .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b967a-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="b967a-108">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="b967a-108">Setting name</span></span> | <span data-ttu-id="b967a-109">Значения</span><span class="sxs-lookup"><span data-stu-id="b967a-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b967a-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b967a-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="b967a-111">`false` — доступ к данным языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="b967a-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="b967a-112">`true` — выполнение в инвариантном режиме</span><span class="sxs-lookup"><span data-stu-id="b967a-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="b967a-113">**Свойство MSBuild**</span><span class="sxs-lookup"><span data-stu-id="b967a-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="b967a-114">`false` — доступ к данным языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="b967a-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="b967a-115">`true` — выполнение в инвариантном режиме</span><span class="sxs-lookup"><span data-stu-id="b967a-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="b967a-116">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="b967a-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="b967a-117">`0` — доступ к данным языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="b967a-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="b967a-118">`1` — выполнение в инвариантном режиме</span><span class="sxs-lookup"><span data-stu-id="b967a-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="b967a-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="b967a-119">Examples</span></span>

<span data-ttu-id="b967a-120">Файл *runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="b967a-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="b967a-121">Файл проекта:</span><span class="sxs-lookup"><span data-stu-id="b967a-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="b967a-122">Era year ranges (Диапазоны лет эры)</span><span class="sxs-lookup"><span data-stu-id="b967a-122">Era year ranges</span></span>

- <span data-ttu-id="b967a-123">Определяет, являются ли проверки диапазона для календарей, поддерживающих несколько эр, нестрогими, или даты, превышающие диапазон дат эры, вызывают <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="b967a-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="b967a-124">По умолчанию: проверки диапазонов нестрогие (`false`).</span><span class="sxs-lookup"><span data-stu-id="b967a-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="b967a-125">Дополнительные сведения см. в разделе [Календари, эры и диапазоны дат: нестрогие проверки диапазонов](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="b967a-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="b967a-126">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="b967a-126">Setting name</span></span> | <span data-ttu-id="b967a-127">Значения</span><span class="sxs-lookup"><span data-stu-id="b967a-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b967a-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b967a-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="b967a-129">`false` — нестрогие проверки диапазонов</span><span class="sxs-lookup"><span data-stu-id="b967a-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="b967a-130">`true` — исключение при переполнении</span><span class="sxs-lookup"><span data-stu-id="b967a-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="b967a-131">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="b967a-131">**Environment variable**</span></span> | <span data-ttu-id="b967a-132">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b967a-132">N/A</span></span> | <span data-ttu-id="b967a-133">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b967a-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="b967a-134">Japanese date parsing (Анализ дат на японском языке)</span><span class="sxs-lookup"><span data-stu-id="b967a-134">Japanese date parsing</span></span>

- <span data-ttu-id="b967a-135">Определяет, успешно ли анализируется строка, содержащая "1" или "Ганнен" в качестве года, либо поддерживается только значение "1".</span><span class="sxs-lookup"><span data-stu-id="b967a-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="b967a-136">По умолчанию: анализ строк, содержащих "1" или "Ганнен" в качестве года (`false`).</span><span class="sxs-lookup"><span data-stu-id="b967a-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="b967a-137">Дополнительные сведения см. в разделе [Представление дат в календарях с несколькими эрами](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="b967a-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="b967a-138">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="b967a-138">Setting name</span></span> | <span data-ttu-id="b967a-139">Значения</span><span class="sxs-lookup"><span data-stu-id="b967a-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b967a-140">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b967a-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="b967a-141">`false` — поддерживается "Ганнен" или "1"</span><span class="sxs-lookup"><span data-stu-id="b967a-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="b967a-142">`true` — поддерживается только "1"</span><span class="sxs-lookup"><span data-stu-id="b967a-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="b967a-143">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="b967a-143">**Environment variable**</span></span> | <span data-ttu-id="b967a-144">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b967a-144">N/A</span></span> | <span data-ttu-id="b967a-145">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b967a-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="b967a-146">Japanese year format (Японский формат года)</span><span class="sxs-lookup"><span data-stu-id="b967a-146">Japanese year format</span></span>

- <span data-ttu-id="b967a-147">Определяет, форматируется ли первый год японской календарной эры как "Ганнен" или как число.</span><span class="sxs-lookup"><span data-stu-id="b967a-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="b967a-148">По умолчанию: первый год форматируется как "Ганнен" (`false`).</span><span class="sxs-lookup"><span data-stu-id="b967a-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="b967a-149">Дополнительные сведения см. в разделе [Представление дат в календарях с несколькими эрами](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="b967a-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="b967a-150">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="b967a-150">Setting name</span></span> | <span data-ttu-id="b967a-151">Значения</span><span class="sxs-lookup"><span data-stu-id="b967a-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b967a-152">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b967a-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="b967a-153">`false` — формат в виде "Ганнен"</span><span class="sxs-lookup"><span data-stu-id="b967a-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="b967a-154">`true` — формат в виде числа</span><span class="sxs-lookup"><span data-stu-id="b967a-154">`true` - format as number</span></span> |
| <span data-ttu-id="b967a-155">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="b967a-155">**Environment variable**</span></span> | <span data-ttu-id="b967a-156">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b967a-156">N/A</span></span> | <span data-ttu-id="b967a-157">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b967a-157">N/A</span></span> |
