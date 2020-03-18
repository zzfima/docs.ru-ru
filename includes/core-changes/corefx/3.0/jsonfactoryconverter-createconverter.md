---
ms.openlocfilehash: 3bce796191e0ebe6dbe4650457abe5a20c383f02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147566"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="1eca1-101">Изменение сигнатуры JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="1eca1-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="1eca1-102">В целях упрощения формирования классов <xref:System.Text.Json.Serialization.JsonConverterFactory> метод <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> стал общедоступным и получил второй аргумент типа <xref:System.Text.Json.JsonSerializerOptions>.</span><span class="sxs-lookup"><span data-stu-id="1eca1-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1eca1-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="1eca1-103">Change description</span></span>

<span data-ttu-id="1eca1-104">Сигнатура метода `CreateConverter` в .NET Core до версии 3.0 (предварительная версия 8) имела вид:</span><span class="sxs-lookup"><span data-stu-id="1eca1-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="1eca1-105">В .NET Core 3.0 (предварительная версия 8) и более поздних версиях она имеет вид:</span><span class="sxs-lookup"><span data-stu-id="1eca1-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="1eca1-106">До этого изменения было сложно создать запечатанные фабричные преобразователи, так как не существовало простого способа получить <xref:System.Text.Json.Serialization.JsonConverter%601>.</span><span class="sxs-lookup"><span data-stu-id="1eca1-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="1eca1-107">Превращение фабричного метода в открытый, а также передача текущего <xref:System.Text.Json.JsonSerializerOptions> обеспечивают гораздо более гибкое формирование.</span><span class="sxs-lookup"><span data-stu-id="1eca1-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1eca1-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="1eca1-108">Version introduced</span></span>

<span data-ttu-id="1eca1-109">3.0 (предварительная версия 8)</span><span class="sxs-lookup"><span data-stu-id="1eca1-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1eca1-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="1eca1-110">Recommended action</span></span>

<span data-ttu-id="1eca1-111">Производные классы должны быть обновлены и перекомпилированы.</span><span class="sxs-lookup"><span data-stu-id="1eca1-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1eca1-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="1eca1-112">Affected APIs</span></span>

- <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
