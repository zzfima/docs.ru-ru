---
ms.openlocfilehash: b57e0acb03a99f33460a7b6c880280b37e01a17b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859282"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a>Защита транспорта WCF поддерживает сертификаты, сохраненные с помощью CNG

|   |   |
|---|---|
|Подробнее|Начиная с приложений, предназначенных для .NET Framework 4.6.2, защита транспорта WCF поддерживает сертификаты, сохраненные с использованием библиотеки шифрования Windows (CNG). Эта поддержка ограничивается сертификатами с открытым ключом, длина экспоненты которого не превышает 32 бита. Если приложение предназначено для .NET Framework 4.6.2, эта функция включена по умолчанию. В более ранних версиях платформы .NET Framework попытка использовать сертификаты X509 с поставщиком хранилища ключей CSG вызывала исключение.|
|Предложение|Для приложений, которые предназначены для .NET Framework 4.6.1 и более ранних версий, но работают в .NET Framework 4.6.2, можно включить поддержку сертификатов CNG, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config или web.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableCngCertificates=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Это также можно сделать программно с помощью следующего кода:<pre><code class="lang-cs">private const string DisableCngCertificates = @&quot;Switch.System.ServiceModel.DisableCngCertificate&quot;;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, false);&#13;&#10;</code></pre><pre><code class="lang-vb">Const DisableCngCertificates As String = &quot;Switch.System.ServiceModel.DisableCngCertificates&quot;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, False)&#13;&#10;</code></pre>Обратите внимание, что из-за этого изменения любой код обработки исключений, который зависит от неудачной попытки инициировать защищенное взаимодействие с сертификатом CNG, больше не будет выполняться.|
|Область|Дополнительный номер|
|Version|4.6.2|
|Type|Изменение целевой платформы|
