---
ms.openlocfilehash: e6e10b2ec451c07bf397cbdcac51ef57c29dab47
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568239"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="7b433-101">Тип исключения сериализатора JSON изменен с `JsonException` на `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="7b433-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="7b433-102">В .NET Core 3.0 (предварительные версии 6–8) при обнаружении неподдерживаемого типа производной коллекции сериализатор выдает исключение <xref:System.Text.Json.JsonException>.</span><span class="sxs-lookup"><span data-stu-id="7b433-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="7b433-103">Начиная с .NET Core 3.0 (предварительная версия 9) сериализатор выдает вместо него исключение <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="7b433-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7b433-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="7b433-104">Change description</span></span>

<span data-ttu-id="7b433-105">В .NET Core 3.0 (предварительные версии 6–8) при обнаружении неподдерживаемого типа производной коллекции сериализатор выдает исключение <xref:System.Text.Json.JsonException>.</span><span class="sxs-lookup"><span data-stu-id="7b433-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="7b433-106">*Неподдерживаемый тип производной коллекции* — это любой тип коллекции, который нельзя назначить одному из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="7b433-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [<span data-ttu-id="7b433-107">IDictionary\<String,T></span><span class="sxs-lookup"><span data-stu-id="7b433-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="7b433-108">Начиная с .NET Core 3.0 (предварительная версия 9) при обнаружении неподдерживаемого типа коллекции сериализатор выдает исключение <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="7b433-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="7b433-109">Новый тип исключения лучше отражает причину сбоя операции десериализации.</span><span class="sxs-lookup"><span data-stu-id="7b433-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7b433-110">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="7b433-110">Version introduced</span></span>

<span data-ttu-id="7b433-111">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="7b433-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7b433-112">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="7b433-112">Recommended action</span></span>

<span data-ttu-id="7b433-113">Если при десериализации вы выполняете перехват исключений <xref:System.Text.Json.JsonException>, рекомендуем также настроить перехват исключений <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="7b433-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="7b433-114">Категория</span><span class="sxs-lookup"><span data-stu-id="7b433-114">Category</span></span>

<span data-ttu-id="7b433-115">CoreFX</span><span class="sxs-lookup"><span data-stu-id="7b433-115">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7b433-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="7b433-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
