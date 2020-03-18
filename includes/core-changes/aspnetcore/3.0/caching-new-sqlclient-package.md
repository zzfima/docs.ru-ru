---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "73198551"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a>Кэширование. Microsoft.Extensions.Caching.SqlServer использует новый пакет SqlClient

Пакет `Microsoft.Extensions.Caching.SqlServer` будет использовать новый пакет `Microsoft.Data.SqlClient` вместо пакета `System.Data.SqlClient`. Это изменение может привести к незначительным критическим изменениям в поведении. См. [обзор Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Пакет `Microsoft.Extensions.Caching.SqlServer` использовал пакет `System.Data.SqlClient`.

#### <a name="new-behavior"></a>Новое поведение

`Microsoft.Extensions.Caching.SqlServer` теперь использует пакет `Microsoft.Data.SqlClient`.

#### <a name="reason-for-change"></a>Причина изменения

`Microsoft.Data.SqlClient` — это новый пакет, созданный на основе `System.Data.SqlClient`. С этого момента в нем будут поддерживаться все новые функции.

#### <a name="recommended-action"></a>Рекомендованное действие

Клиентам не нужно беспокоиться об этом критическом изменении, если только они не использовали типы, возвращаемые пакетом `Microsoft.Extensions.Caching.SqlServer` и приводимые к типам `System.Data.SqlClient`. Например, при приведении `DbConnection` к [старому типу SqlConnection](xref:System.Data.SqlClient.SqlConnection), нужно будет изменить приведение на новый тип `Microsoft.Data.SqlClient.SqlConnection`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
