---
title: Параметры конфигурации глобализации
description: Вы можете узнать о параметрах времени выполнения, настраивающих аспекты глобализации для приложения .NET Core, например способа анализа дат на японском языке.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 0571c64eff5b38aafa37026fb2ba7f4aef778beb
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998843"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="b851b-103">Параметры конфигурации времени выполнения для глобализации</span><span class="sxs-lookup"><span data-stu-id="b851b-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="b851b-104">Invariant mode (Инвариантный режим)</span><span class="sxs-lookup"><span data-stu-id="b851b-104">Invariant mode</span></span>

- <span data-ttu-id="b851b-105">Определяет, выполняется ли приложение .NET Core в инвариантном режиме глобализации без доступа к данным и поведению, зависящим от языка и региональных параметров, и имеет ли оно доступ к данным языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="b851b-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="b851b-106">По умолчанию: выполнение приложения с доступом к данным языка и региональных параметров (`false`).</span><span class="sxs-lookup"><span data-stu-id="b851b-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="b851b-107">Дополнительные сведения см. в статье [Инвариантный режим глобализации .NET Core](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b851b-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="b851b-108">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="b851b-108">Setting name</span></span> | <span data-ttu-id="b851b-109">Значения</span><span class="sxs-lookup"><span data-stu-id="b851b-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b851b-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b851b-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="b851b-111">`false` — доступ к данным языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="b851b-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="b851b-112">`true` — выполнение в инвариантном режиме</span><span class="sxs-lookup"><span data-stu-id="b851b-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="b851b-113">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="b851b-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="b851b-114">`0` — доступ к данным языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="b851b-114">`0` - access to cultural data</span></span><br/><span data-ttu-id="b851b-115">`1` — выполнение в инвариантном режиме</span><span class="sxs-lookup"><span data-stu-id="b851b-115">`1` - run in invariant mode</span></span> |

## <a name="era-year-ranges"></a><span data-ttu-id="b851b-116">Era year ranges (Диапазоны лет эры)</span><span class="sxs-lookup"><span data-stu-id="b851b-116">Era year ranges</span></span>

- <span data-ttu-id="b851b-117">Определяет, являются ли проверки диапазона для календарей, поддерживающих несколько эр, нестрогими, или даты, превышающие диапазон дат эры, вызывают <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="b851b-117">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="b851b-118">По умолчанию: проверки диапазонов нестрогие (`false`).</span><span class="sxs-lookup"><span data-stu-id="b851b-118">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="b851b-119">Дополнительные сведения см. в разделе [Календари, эры и диапазоны дат: нестрогие проверки диапазонов](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="b851b-119">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="b851b-120">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="b851b-120">Setting name</span></span> | <span data-ttu-id="b851b-121">Значения</span><span class="sxs-lookup"><span data-stu-id="b851b-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b851b-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b851b-122">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="b851b-123">`false` — нестрогие проверки диапазонов</span><span class="sxs-lookup"><span data-stu-id="b851b-123">`false` - relaxed range checks</span></span><br/><span data-ttu-id="b851b-124">`true` — исключение при переполнении</span><span class="sxs-lookup"><span data-stu-id="b851b-124">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="b851b-125">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="b851b-125">**Environment variable**</span></span> | <span data-ttu-id="b851b-126">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b851b-126">N/A</span></span> | <span data-ttu-id="b851b-127">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b851b-127">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="b851b-128">Japanese date parsing (Анализ дат на японском языке)</span><span class="sxs-lookup"><span data-stu-id="b851b-128">Japanese date parsing</span></span>

- <span data-ttu-id="b851b-129">Определяет, успешно ли анализируется строка, содержащая "1" или "Ганнен" в качестве года, либо поддерживается только значение "1".</span><span class="sxs-lookup"><span data-stu-id="b851b-129">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="b851b-130">По умолчанию: анализ строк, содержащих "1" или "Ганнен" в качестве года (`false`).</span><span class="sxs-lookup"><span data-stu-id="b851b-130">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="b851b-131">Дополнительные сведения см. в разделе [Представление дат в календарях с несколькими эрами](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="b851b-131">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="b851b-132">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="b851b-132">Setting name</span></span> | <span data-ttu-id="b851b-133">Значения</span><span class="sxs-lookup"><span data-stu-id="b851b-133">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b851b-134">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b851b-134">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="b851b-135">`false` — поддерживается "Ганнен" или "1"</span><span class="sxs-lookup"><span data-stu-id="b851b-135">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="b851b-136">`true` — поддерживается только "1"</span><span class="sxs-lookup"><span data-stu-id="b851b-136">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="b851b-137">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="b851b-137">**Environment variable**</span></span> | <span data-ttu-id="b851b-138">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b851b-138">N/A</span></span> | <span data-ttu-id="b851b-139">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b851b-139">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="b851b-140">Japanese year format (Японский формат года)</span><span class="sxs-lookup"><span data-stu-id="b851b-140">Japanese year format</span></span>

- <span data-ttu-id="b851b-141">Определяет, форматируется ли первый год японской календарной эры как "Ганнен" или как число.</span><span class="sxs-lookup"><span data-stu-id="b851b-141">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="b851b-142">По умолчанию: первый год форматируется как "Ганнен" (`false`).</span><span class="sxs-lookup"><span data-stu-id="b851b-142">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="b851b-143">Дополнительные сведения см. в разделе [Представление дат в календарях с несколькими эрами](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="b851b-143">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="b851b-144">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="b851b-144">Setting name</span></span> | <span data-ttu-id="b851b-145">Значения</span><span class="sxs-lookup"><span data-stu-id="b851b-145">Values</span></span> |
| - | - | - |
| <span data-ttu-id="b851b-146">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="b851b-146">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="b851b-147">`false` — формат в виде "Ганнен"</span><span class="sxs-lookup"><span data-stu-id="b851b-147">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="b851b-148">`true` — формат в виде числа</span><span class="sxs-lookup"><span data-stu-id="b851b-148">`true` - format as number</span></span> |
| <span data-ttu-id="b851b-149">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="b851b-149">**Environment variable**</span></span> | <span data-ttu-id="b851b-150">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b851b-150">N/A</span></span> | <span data-ttu-id="b851b-151">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b851b-151">N/A</span></span> |
