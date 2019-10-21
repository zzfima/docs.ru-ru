---
ms.openlocfilehash: fc17efbad63ee43ddcdfd14e2fbd1557d2b3d31c
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72424792"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a>TLS 1.x по умолчанию передает флаг SCH_SEND_AUX_RECORD базовому API SCHANNEL

|   |   |
|---|---|
|Подробные сведения|При использовании TLS 1.x .NET Framework зависит от базового интерфейса API Windows SCHANNEL. Начиная с .NET Framework 4.6 флаг [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) передается SCHANNEL по умолчанию. В результате SCHANNEL разбивает данные для шифрования на две отдельных записи. В первой — один байт, а во второй — <em>n</em>–1 байт. В редких случаях это нарушает логику взаимодействия между клиентами и существующими серверами, которая предполагает, что данные находятся в одной записи.|
|Предложение|Если это изменение нарушает связь с существующим сервером, вы можете отключить отправку флага [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) и восстановить предыдущее поведение, при котором данные не разделяются на две записи, добавив следующий переключатель в элемент [<](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в разделе [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontEnableSchSendAuxRecord=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] Этот параметр предоставляется исключительно для обратной совместимости. Его использование в других целях не рекомендуется.</blockquote> |
|Область|Пограничный случай|
|Версия|4.6|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|
