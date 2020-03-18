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
# <a name="run-time-configuration-options-for-globalization"></a>Параметры конфигурации времени выполнения для глобализации

## <a name="invariant-mode"></a>Invariant mode (Инвариантный режим)

- Определяет, выполняется ли приложение .NET Core в инвариантном режиме глобализации без доступа к данным и поведению, зависящим от языка и региональных параметров, и имеет ли оно доступ к данным языка и региональных параметров.
- По умолчанию: выполнение приложения с доступом к данным языка и региональных параметров (`false`).
- Дополнительные сведения см. в статье [Инвариантный режим глобализации .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `System.Globalization.Invariant` | `false` — доступ к данным языка и региональных параметров<br/>`true` — выполнение в инвариантном режиме |
| **Свойство MSBuild** | `InvariantGlobalization` | `false` — доступ к данным языка и региональных параметров<br/>`true` — выполнение в инвариантном режиме |
| **Переменная среды** | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | `0` — доступ к данным языка и региональных параметров<br/>`1` — выполнение в инвариантном режиме |

### <a name="examples"></a>Примеры

Файл *runtimeconfig.json*

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

Файл проекта:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a>Era year ranges (Диапазоны лет эры)

- Определяет, являются ли проверки диапазона для календарей, поддерживающих несколько эр, нестрогими, или даты, превышающие диапазон дат эры, вызывают <xref:System.ArgumentOutOfRangeException>.
- По умолчанию: проверки диапазонов нестрогие (`false`).
- Дополнительные сведения см. в разделе [Календари, эры и диапазоны дат: нестрогие проверки диапазонов](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | `false` — нестрогие проверки диапазонов<br/>`true` — исключение при переполнении |
| **Переменная среды** | Н/Д | Н/Д |

## <a name="japanese-date-parsing"></a>Japanese date parsing (Анализ дат на японском языке)

- Определяет, успешно ли анализируется строка, содержащая "1" или "Ганнен" в качестве года, либо поддерживается только значение "1".
- По умолчанию: анализ строк, содержащих "1" или "Ганнен" в качестве года (`false`).
- Дополнительные сведения см. в разделе [Представление дат в календарях с несколькими эрами](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false` — поддерживается "Ганнен" или "1"<br/>`true` — поддерживается только "1" |
| **Переменная среды** | Н/Д | Н/Д |

## <a name="japanese-year-format"></a>Japanese year format (Японский формат года)

- Определяет, форматируется ли первый год японской календарной эры как "Ганнен" или как число.
- По умолчанию: первый год форматируется как "Ганнен" (`false`).
- Дополнительные сведения см. в разделе [Представление дат в календарях с несколькими эрами](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Имя параметра | Значения |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false` — формат в виде "Ганнен"<br/>`true` — формат в виде числа |
| **Переменная среды** | Н/Д | Н/Д |
