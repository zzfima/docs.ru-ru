---
ms.openlocfilehash: f5b0064f9f01923c6353fd8e2b274bd7407ccbd8
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237449"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a>Изменение сигнатуры JsonFactoryConverter.CreateConverter

В целях упрощения формирования классов <xref:System.Text.Json.Serialization.JsonConverterFactory> метод <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> стал общедоступным и получил второй аргумент типа <xref:System.Text.Json.JsonSerializerOptions>.

#### <a name="change-description"></a>Описание изменений

Сигнатура метода `CreateConverter` в .NET Core до версии 3.0 (предварительная версия 8) имела вид: 

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

В .NET Core 3.0 (предварительная версия 8) и более поздних версиях она имеет вид:

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

До этого изменения было сложно создать запечатанные фабричные преобразователи, так как не существовало простого способа получить <xref:System.Text.Json.Serialization.JsonConverter%601>. Превращение фабричного метода в открытый, а также передача текущего <xref:System.Text.Json.JsonSerializerOptions> обеспечивают гораздо более гибкое формирование.

#### <a name="version-introduced"></a>Представленная версия

3.0 (предварительная версия 8)

#### <a name="recommended-action"></a>Рекомендуемое действие

Производные классы должны быть обновлены и перекомпилированы.

#### <a name="affected-apis"></a>Затронутые API

<xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>.

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
