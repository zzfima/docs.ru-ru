---
ms.openlocfilehash: ce7e2db3f74ec24f47b1c224335451c997c4c349
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761063"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a>Привязка WCF с режимом безопасности TransportWithMessageCredential

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.6.1 привязку WCF, которая использует режим безопасности TransportWithMessageCredential, можно настроить для получения сообщений с неподписанными заголовками &quot;to&quot; для асимметричных ключей безопасности. По умолчанию неподписанные заголовки &quot;to&quot; будут отклоняться в .NET Framework 4.6.1. Они будут приниматься только в случае перевода приложения на новый режим с помощью переключателя конфигурации Switch.System.ServiceModel.AllowUnsignedToHeader.|
|Предложение|Поскольку это возможность, включаемая пользователем, она не должна влиять на поведение существующих приложений.<br/>Для включения или отключения нового поведения используйте следующий параметр конфигурации:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.AllowUnsignedToHeader=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Прозрачный|
|Версия|4.6.1|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li></ul>|

