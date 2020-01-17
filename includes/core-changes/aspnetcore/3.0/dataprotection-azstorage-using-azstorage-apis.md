---
ms.openlocfilehash: db70596552ffd699156e1b7a55cb1e944596f077
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901766"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a>Защита данных. DataProtection.AzureStorage использует новые API службы хранилища Azure

<xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> зависит от [библиотек службы хранилища Azure](https://github.com/Azure/azure-storage-net). Эти библиотеки переименовали свои сборки, пакеты и пространства имен. Начиная с ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` использует новые API и пакеты с префиксом `Microsoft.Azure.Storage.`.

Если у вас возникли вопросы об API службы хранилища Azure, см. страницу <https://github.com/Azure/azure-storage-net>. Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Пакет ссылался на пакет `WindowsAzure.Storage` NuGet.

#### <a name="new-behavior"></a>Новое поведение

Пакет ссылается на пакет `Microsoft.Azure.Storage.Blob` NuGet.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение позволяет `Microsoft.AspNetCore.DataProtection.AzureStorage` переходить к рекомендуемым пакетам службы хранилища Azure.

#### <a name="recommended-action"></a>Рекомендованное действие

Если вам по-прежнему нужно использовать старые API службы хранилища Azure с ASP.NET Core 3.0, добавьте прямую зависимость в пакет [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/). Этот пакет можно установить вместе с новыми API `Microsoft.Azure.Storage`.

Во многих случаях обновление включает только изменение инструкций `using` для использования новых пространств имен:

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
