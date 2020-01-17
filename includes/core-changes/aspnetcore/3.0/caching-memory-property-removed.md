---
ms.openlocfilehash: 2c1362d6982206b14475f77700add0bae61da173
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901869"
---
### <a name="caching-compactonmemorypressure-property-removed"></a>Кэширование: свойство CompactOnMemoryPressure удалено

В выпуске ASP.NET Core 3.0 недоступны [устаревшие API MemoryCacheOptions](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).

#### <a name="change-description"></a>Описание изменений

Это изменение реализовано в рамках исправления [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221). Обсуждение этого вопроса см. на странице [dotnet/extensions#1062](https://github.com/dotnet/extensions/issues/1062).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Свойство `MemoryCacheOptions.CompactOnMemoryPressure` было доступно.

#### <a name="new-behavior"></a>Новое поведение

Свойство `MemoryCacheOptions.CompactOnMemoryPressure` было удалено.

#### <a name="reason-for-change"></a>Причина изменения

Автоматическое сжатие кэша приводило к возникновению проблем. Чтобы не допустить непредвиденное поведение, сжимайте кэш только при необходимости.

#### <a name="recommended-action"></a>Рекомендованное действие

Чтобы сжать кэш, выполните приведение с понижением к `MemoryCache` и вызовите `Compact` при необходимости.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
