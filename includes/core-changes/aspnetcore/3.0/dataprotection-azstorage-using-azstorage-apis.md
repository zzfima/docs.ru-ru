---
ms.openlocfilehash: f103c96588bae167216d09a82973a4a7abfb5cc3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394042"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a>Защита данных. DataProtection.AzureStorage использует новые API службы хранилища Azure

<xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> зависит от [библиотек службы хранилища Azure](https://github.com/Azure/azure-storage-net). Эти библиотеки переименовали свои сборки, пакеты и пространства имен. Начиная с ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` использует новые API и пакеты с префиксом `Microsoft.Azure.Storage.`.

Если у вас возникли вопросы об API службы хранилища Azure, см. страницу <https://github.com/Azure/azure-storage-net>. Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#8472](https://github.com/aspnet/AspNetCore/issues/8472).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Пакет ссылался на пакет `WindowsAzure.Storage` NuGet.

#### <a name="new-behavior"></a>Новое поведение

Пакет ссылается на пакет `Microsoft.Azure.Storage.Blob` NuGet.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение позволяет `Microsoft.AspNetCore.DataProtection.AzureStorage` переходить к рекомендуемым пакетам службы хранилища Azure.

#### <a name="recommended-action"></a>Рекомендуемое действие

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

Нет

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
