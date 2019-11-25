---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394377"
---
### <a name="kestrel-empty-https-assembly-removed"></a>Kestrel. Удаление пустой сборки HTTPS

Сборка <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> была удалена.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="reason-for-change"></a>Причина изменения

В ASP.NET Core 2.1 содержимое `Microsoft.AspNetCore.Server.Kestrel.Https` перемещено в <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>. Это изменение выполнено некритическим образом с помощью атрибутов `[TypeForwardedTo]`.

#### <a name="recommended-action"></a>Рекомендуемое действие

- Библиотеки, ссылающиеся на `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0, должны обновить все зависимости ASP.NET Core до версии 2.1 и выше. В противном случае они могут прерывать работу при загрузке в приложение ASP.NET Core 3.0.
- Приложения и библиотеки, предназначенные для ASP.NET Core версии 2.1 и выше, должны удалять все прямые ссылки на пакет `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Нет

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
