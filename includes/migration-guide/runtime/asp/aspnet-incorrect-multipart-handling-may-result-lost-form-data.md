---
ms.openlocfilehash: e6b0387d9d04aa979de289ea0c5caa6c76f4d1be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802668"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a>Неправильная составная обработка ASP.NET может привести к потере данных формы.

|   |   |
|---|---|
|Подробнее|В приложениях, предназначенных для .NET Framework 4.7.2 и более ранних версий, ASP.Net может неправильно выполнять синтаксический анализ составных граничных значений, и это приведет к тому, что данные формы будут недоступны во время выполнения запроса. Приложения, предназначенные для .NET Framework 4.8 или более поздних версий, правильно выполняют синтаксический анализ составных данных, поэтому значения формы доступны во время выполнения запроса.|
|Предложение|Начиная с приложений, выполняемых на .NET Framework 4.8, при нацеливании на .NET Framework 4.8 или более поздней версии с помощью элемента <code>targetFrameworkVersion</code> поведение по умолчанию меняется на удаление разделителей. При нацеливании на предыдущие версии платформы или если <code>targetFrameworkVersion</code> не используется, конечные разделители для некоторых значений по-прежнему возвращаются. Этим поведением можно также явно управлять при помощи <code>appSetting</code>:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Неизвестно|
|Version|4.8|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Web.HttpRequest.Form?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.Files?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
