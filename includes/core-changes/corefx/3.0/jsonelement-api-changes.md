---
ms.openlocfilehash: 79901d0b57816915ca7ea73cfe7fa3d40820434e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568164"
---
### <a name="jsonelement-api-changes"></a>Изменения в API JsonElement

Начиная с .NET Core 3.0 (предварительная версия 7) в некоторые API-интерфейсы <xref:System.Text.Json.JsonElement> были внесены изменения для более удобного обнаружения и использования.

#### <a name="change-description"></a>Описание изменений

В .NET Core 3.0 (предварительная версия 7) в API-интерфейсы <xref:System.Text.Json.JsonElement> были внесены указанные ниже изменения для удобства обнаружения и использования.

1. Из `WriteProperty` удалены все перегрузки методов <xref:System.Text.Json.JsonElement>. Это влияет на следующий код:

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

1. Параметр `WriteValue` переименован в <xref:System.Text.Json.JsonElement.WriteTo%2A>. Это влияет на следующий код:

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. Теперь <xref:System.Text.Json.JsonElement.WriteTo%2A> создает исключение <xref:System.ArgumentNullException>, если соответствующий параметр метода имеет значение `null`.

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 7

#### <a name="recommended-action"></a>Рекомендованное действие

Если эти изменения влияют на ваш код, можно сделать следующее.

- Для перегрузок метода `WriteProperty` в <xref:System.Text.Json.JsonElement> не существует заменяющего API. Вместо этого вместе с методом <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> можно вызвать одну из перегрузок <xref:System.Text.Json.JsonElement.WriteTo%2A>, чтобы достичь того же результата. Пример:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- Переименуйте метод `WriteValue` в <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>. При этом параметр метода остается неизменным. Например, предыдущий код необходимо изменить следующим образом:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- Обработайте исключение <xref:System.ArgumentNullException> в вызовах метода <xref:System.Text.Json.JsonElement.WriteTo%2A>.

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
