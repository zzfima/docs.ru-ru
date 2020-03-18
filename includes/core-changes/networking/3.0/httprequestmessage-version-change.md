---
ms.openlocfilehash: 5ad9c494fd02059e05cc744aad3b06cfc9399995
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77451900"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>Значение по умолчанию HttpRequestMessage.Version изменено на 1.1

Значение свойства <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> по умолчанию изменено с 2.0 на 1.1.

#### <a name="version-introduced"></a>Представленная версия

3,0

#### <a name="change-description"></a>Описание изменений

В .NET Core с 1.0 по 2.0 значением свойства <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> по умолчанию является 1.1. Начиная с .NET Core 2.1 оно было изменено на 2.1.

Начиная с .NET Core 3.0 номер версии по умолчанию, возвращаемый свойством <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>, снова стал 1.1.

#### <a name="recommended-action"></a>Рекомендованное действие

Обновите код, если он зависит от свойства <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>, возвращающего значение по умолчанию 2.0.

#### <a name="category"></a>Категория

Сеть

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-->
