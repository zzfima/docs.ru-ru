---
ms.openlocfilehash: 79901d0b57816915ca7ea73cfe7fa3d40820434e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568164"
---
### <a name="jsonelement-api-changes"></a><span data-ttu-id="2ca40-101">Изменения в API JsonElement</span><span class="sxs-lookup"><span data-stu-id="2ca40-101">JsonElement API changes</span></span>

<span data-ttu-id="2ca40-102">Начиная с .NET Core 3.0 (предварительная версия 7) в некоторые API-интерфейсы <xref:System.Text.Json.JsonElement> были внесены изменения для более удобного обнаружения и использования.</span><span class="sxs-lookup"><span data-stu-id="2ca40-102">Starting with .NET Core 3.0 Preview 7, some <xref:System.Text.Json.JsonElement> APIs have changed to allow for easier discovery and greater usability.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2ca40-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="2ca40-103">Change description</span></span>

<span data-ttu-id="2ca40-104">В .NET Core 3.0 (предварительная версия 7) в API-интерфейсы <xref:System.Text.Json.JsonElement> были внесены указанные ниже изменения для удобства обнаружения и использования.</span><span class="sxs-lookup"><span data-stu-id="2ca40-104">In .NET Core 3.0 Preview 7, <xref:System.Text.Json.JsonElement> APIs have changed as follows to allow for easier discovery and greater usability.</span></span>

1. <span data-ttu-id="2ca40-105">Из `WriteProperty` удалены все перегрузки методов <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="2ca40-105">All `WriteProperty` method overloads were removed from <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="2ca40-106">Это влияет на следующий код:</span><span class="sxs-lookup"><span data-stu-id="2ca40-106">This affects code such as the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
      JsonElement root = doc.RootElement;
      root.WriteProperty(propertyNameString, writer);
      // ..
      root.WriteProperty(propertyNameSpan, writer);
      // ..
      root.WriteProperty(propertyNameJsonEncoded, writer);
      // ..
      root.WriteProperty(utf8PropertyName, writer);
      //..
   }
   ```

1. <span data-ttu-id="2ca40-107">Параметр `WriteValue` переименован в <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ca40-107">`WriteValue` was renamed as <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span></span> <span data-ttu-id="2ca40-108">Это влияет на следующий код:</span><span class="sxs-lookup"><span data-stu-id="2ca40-108">This affects code such as the following:</span></span>

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. <span data-ttu-id="2ca40-109">Теперь <xref:System.Text.Json.JsonElement.WriteTo%2A> создает исключение <xref:System.ArgumentNullException>, если соответствующий параметр метода имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="2ca40-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> now throws an <xref:System.ArgumentNullException> when its method parameter is `null`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2ca40-110">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="2ca40-110">Version introduced</span></span>

<span data-ttu-id="2ca40-111">3.0, предварительная версия 7</span><span class="sxs-lookup"><span data-stu-id="2ca40-111">3.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2ca40-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="2ca40-112">Recommended action</span></span>

<span data-ttu-id="2ca40-113">Если эти изменения влияют на ваш код, можно сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="2ca40-113">If your code is affected by these changes, you can do the following:</span></span>

- <span data-ttu-id="2ca40-114">Для перегрузок метода `WriteProperty` в <xref:System.Text.Json.JsonElement> не существует заменяющего API.</span><span class="sxs-lookup"><span data-stu-id="2ca40-114">There is no replacement API for the `WriteProperty` overloads in <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="2ca40-115">Вместо этого вместе с методом <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> можно вызвать одну из перегрузок <xref:System.Text.Json.JsonElement.WriteTo%2A>, чтобы достичь того же результата.</span><span class="sxs-lookup"><span data-stu-id="2ca40-115">Instead, you can call one of the <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> overloads along with the <xref:System.Text.Json.JsonElement.WriteTo%2A> method to achieve the same result.</span></span> <span data-ttu-id="2ca40-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="2ca40-116">For example:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="2ca40-117">Переименуйте метод `WriteValue` в <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span><span class="sxs-lookup"><span data-stu-id="2ca40-117">Rename the `WriteValue` method to <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span></span> <span data-ttu-id="2ca40-118">При этом параметр метода остается неизменным.</span><span class="sxs-lookup"><span data-stu-id="2ca40-118">The method parameter remains unchanged.</span></span> <span data-ttu-id="2ca40-119">Например, предыдущий код необходимо изменить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2ca40-119">For example, the previous code should be changed to the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="2ca40-120">Обработайте исключение <xref:System.ArgumentNullException> в вызовах метода <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ca40-120">Handle the <xref:System.ArgumentNullException> in calls to the <xref:System.Text.Json.JsonElement.WriteTo%2A> method.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2ca40-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2ca40-121">Affected APIs</span></span>

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
