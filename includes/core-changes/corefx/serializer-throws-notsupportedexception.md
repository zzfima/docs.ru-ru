---
ms.openlocfilehash: 39d1b2dba8077bf9bf998775f8967d455f36b549
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119086"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a>Тип исключения сериализатора JSON изменен с `JsonException` на `NotSupportedException`

В .NET Core 3.0 (предварительные версии 6–8) при обнаружении неподдерживаемого типа производной коллекции сериализатор выдает исключение <xref:System.Text.Json.JsonException>. Начиная с .NET Core 3.0 (предварительная версия 9) сериализатор выдает вместо него исключение <xref:System.NotSupportedException>.

#### <a name="change-description"></a>Описание изменений

В .NET Core 3.0 (предварительные версии 6–8) при обнаружении неподдерживаемого типа производной коллекции сериализатор выдает исключение <xref:System.Text.Json.JsonException>. *Неподдерживаемый тип производной коллекции* — это любой тип коллекции, который нельзя назначить одному из следующих типов:

 - <xref:System.Collections.IList>
 - <xref:System.Collections.Generic.ICollection%601>
 - <xref:System.Collections.Generic.Stack%601>
 - <xref:System.Collections.Generic.Queue%601>`
 - <xref:System.Collections.IDictionary>
 - [IDictionary\<String,T>](xref:System.Collections.Generic.IDictionary%602)

Начиная с .NET Core 3.0 (предварительная версия 9) при обнаружении неподдерживаемого типа коллекции сериализатор выдает исключение <xref:System.NotSupportedException>. Новый тип исключения лучше отражает причину сбоя операции десериализации.

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 9

#### <a name="recommended-action"></a>Рекомендуемое действие

Если при десериализации вы выполняете перехват исключений <xref:System.Text.Json.JsonException>, рекомендуем также настроить перехват исключений <xref:System.NotSupportedException>.

#### <a name="category"></a>Категория

CoreFX

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
