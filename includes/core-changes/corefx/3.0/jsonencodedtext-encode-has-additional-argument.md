---
ms.openlocfilehash: f5ae4669c85ae4f5d57d88ab55f6e1c758a625a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147592"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a>Методы JsonEncodedText.Encode содержат дополнительный аргумент JavaScriptEncoder

Начиная с .NET Core 3.0 (предварительная версия 8) методы <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> содержат необязательный аргумент <xref:System.Text.Encodings.Web.JavaScriptEncoder>.

#### <a name="change-description"></a>Описание изменений

.NET Core 3.0 включает новый тип xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>. Начиная с .NET Core 3 0 (предварительная версия 8) сигнатура всех перегрузок метода <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> включает необязательный параметр <xref:System.Text.Encodings.Web.JavaScriptEncoder>. Это изменение позволяет использовать другой или пользовательский кодировщик.

Сигнатура методов `Encode` в NET Core 3.0 (предварительная версия 7):

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value);
        public static JsonEncodedText Encode(string value);
    }
}
```

Сигнатура тех же методов `Encode` в NET Core 3.0 (предварительная версия 8 и последующие версии):

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(string value, JavaScriptEncoder encoder = null);
    }
}
```

#### <a name="version-introduced"></a>Представленная версия

.NET Core 3.0 (предварительная версия 8)

#### <a name="recommended-action"></a>Рекомендованное действие

Это критическое изменение касается только двоичного кода. При повторной компиляции для .NET Core 3.0 (предварительная версия 8 и последующие версии) все проблемы среды выполнения будут исправлены.

#### <a name="category"></a>Категория

CoreFX

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
