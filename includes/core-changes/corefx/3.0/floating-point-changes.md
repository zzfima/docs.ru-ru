---
ms.openlocfilehash: ce4f09908b1025e8e5a0380c9bf035c6b0db479a
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568210"
---
### <a name="floating-point-formatting-and-parsing-behavior-changed"></a>Изменено поведение форматирования и анализа при наличии плавающей запятой

Поведение форматирования и анализа при наличии плавающей запятой (с помощью типов <xref:System.Double> и <xref:System.Single>) теперь совместимо со стандартами IEEE.

#### <a name="change-description"></a>Описание изменений

В .NET Core 2.2 и более ранних версиях форматирование с помощью <xref:System.Double.ToString%2A?displayProperty=nameWithType> и <xref:System.Single.ToString%2A?displayProperty=nameWithType> и анализ с помощью <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType> и <xref:System.Single.TryParse%2A?displayProperty=nameWithType> не были совместимы со стандартами IEEE. В результате невозможно гарантировать, что значение будет соответствовать какой-либо поддерживаемой стандартной или пользовательской строке формата. Для некоторых входных данных попытка проанализировать отформатированное значение может завершиться ошибкой, а для других — проанализированное значение не равно исходному.

Начиная с .NET Core 3.0, операции анализа и форматирования совместимы со стандартом IEEE 754. Благодаря этому поведение типов с плавающей запятой в .NET соответствует их поведению в языках, совместимых с IEEE, например C#. Дополнительные сведения см. в записи блога [Улучшения в синтаксическом анализе и форматировании плавающей запятой в .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендуемое действие

В разделе "Потенциальное влияние на существующий код" записи блога [Улучшения в синтаксическом анализе и форматировании плавающей запятой в .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) предлагаются изменения, которые можно внести в код, если по сравнению с .NET Core 2.2 поведение приложения изменилось. Как правило, предполагается использование другой стандартной или пользовательской строки формата для обеспечения требуемого поведения. Для некоторых результатов обходное решение может отсутствовать, если ранее они были неверны.

#### <a name="category"></a>Категория

CoreFX

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Double.ToString%2A?displayProperty=nameWithType>
- <xref:System.Single.ToString%2A?displayProperty=nameWithType>
- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `Overload:System.Double.ToString`
- `Overload:System.Single.ToString`
- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
