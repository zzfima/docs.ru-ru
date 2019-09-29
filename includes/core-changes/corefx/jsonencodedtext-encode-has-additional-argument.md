---
ms.openlocfilehash: 377f22409558c21d1c57f6214c13572dedf9e419
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216951"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a><span data-ttu-id="f689e-101">Методы JsonEncodedText.Encode содержат дополнительный аргумент JavaScriptEncoder</span><span class="sxs-lookup"><span data-stu-id="f689e-101">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>

<span data-ttu-id="f689e-102">Начиная с .NET Core 3.0 (предварительная версия 8) методы <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> содержат необязательный аргумент <xref:System.Text.Encodings.Web.JavaScriptEncoder>.</span><span class="sxs-lookup"><span data-stu-id="f689e-102">Starting with .NET Core 3.0 Preview 8, the <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> methods contain an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> argument.</span></span>

#### <a name="details"></a><span data-ttu-id="f689e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="f689e-103">Details</span></span>

<span data-ttu-id="f689e-104">.NET Core 3.0 включает новый тип xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f689e-104">.NET Core 3.0 includes a new type, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f689e-105">Начиная с .NET Core 3 0 (предварительная версия 8) сигнатура всех перегрузок метода <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> включает необязательный параметр <xref:System.Text.Encodings.Web.JavaScriptEncoder>.</span><span class="sxs-lookup"><span data-stu-id="f689e-105">Starting with .NET Core 3.0 Preview 8, the signature of all <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> method overloads has changed to include an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> parameter.</span></span> <span data-ttu-id="f689e-106">Это изменение позволяет использовать другой или пользовательский кодировщик.</span><span class="sxs-lookup"><span data-stu-id="f689e-106">This change was made to allow for a different or custom encoder.</span></span>

<span data-ttu-id="f689e-107">Сигнатура методов `Encode` в NET Core 3.0 (предварительная версия 7):</span><span class="sxs-lookup"><span data-stu-id="f689e-107">The signature of the `Encode` methods in .NET Core 3.0 Preview 7 is:</span></span>

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

<span data-ttu-id="f689e-108">Сигнатура тех же методов `Encode` в NET Core 3.0 (предварительная версия 8 и последующие версии):</span><span class="sxs-lookup"><span data-stu-id="f689e-108">The signature of the same `Encode` methods in .NET Core 3.0 Preview 8 and later versions is:</span></span>

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

#### <a name="version-introduced"></a><span data-ttu-id="f689e-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="f689e-109">Version introduced</span></span>

<span data-ttu-id="f689e-110">.NET Core 3.0 (предварительная версия 8)</span><span class="sxs-lookup"><span data-stu-id="f689e-110">.NET Core 3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f689e-111">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="f689e-111">Recommended action</span></span>

<span data-ttu-id="f689e-112">Это критическое изменение касается только двоичного кода. При повторной компиляции для .NET Core 3.0 (предварительная версия 8 и последующие версии) все проблемы среды выполнения будут исправлены.</span><span class="sxs-lookup"><span data-stu-id="f689e-112">This is a binary breaking change only; a recompile against .NET Core 3.0 Preview 8 or a later version will fix any runtime issues.</span></span>

#### <a name="category"></a><span data-ttu-id="f689e-113">Категория</span><span class="sxs-lookup"><span data-stu-id="f689e-113">Category</span></span>

<span data-ttu-id="f689e-114">CoreFX</span><span class="sxs-lookup"><span data-stu-id="f689e-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f689e-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f689e-115">Affected APIs</span></span>

<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
