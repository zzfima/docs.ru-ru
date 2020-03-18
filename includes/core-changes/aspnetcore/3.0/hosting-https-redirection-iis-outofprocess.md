---
ms.openlocfilehash: eb3fa768a491f6c0ff4b15479beabd71b0670338
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937297"
---
### <a name="hosting-https-redirection-enabled-for-iis-out-of-process-apps"></a>Размещение. Для приложений IIS вне процесса включено перенаправление HTTPS

В [ASP.NET Core Module (ANCM)](/aspnet/core/host-and-deploy/aspnet-core-module) версии 13.0.19218.0 для размещения с помощью IIS вне процесса можно реализовать существующую функцию перенаправления HTTPS для приложений ASP.NET Core 3.0 и 2.2.

Обсуждение этого вопроса см. на странице [dotnet/AspNetCore#15243](https://github.com/dotnet/AspNetCore/issues/15243).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

В шаблоне проекта ASP.NET Core 2.1 впервые представлена поддержка методов HTTPS промежуточного слоя, таких как <xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A> и <xref:Microsoft.AspNetCore.Builder.HstsBuilderExtensions.UseHsts%2A>. Для включения перенаправления HTTPS требовалось добавить конфигурацию, поскольку приложения, находящиеся в разработке, не используют порт по умолчанию 443. [Протокол HSTS](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html) активен только в том случае, если запрос уже использует протокол HTTPS. По умолчанию localhost пропускается.

#### <a name="new-behavior"></a>Новое поведение

В ASP.NET Core 3.0 [усовершенствован](https://github.com/dotnet/AspNetCore/pull/4685) сценарий IIS HTTPS. Благодаря этому усовершенствованию приложение может обнаруживать порты HTTPS сервера и сделать так, что `UseHttpsRedirection` будет работать по умолчанию. Внутрипроцессный компонент выполнял обнаружение порта с помощью функции `IServerAddresses`, которая влияет только на приложения ASP.NET Core 3.0, поскольку внутрипроцессная библиотека имеет версию платформы. Внепроцессный компонент был изменен — теперь он автоматически добавляет переменную среды `ASPNETCORE_HTTPS_PORT`. Это изменение повлияло на приложения ASP.NET Core 2.2 и 3.0, поскольку внепроцессный компонент используется совместно глобально. Данное изменение не затрагивает приложения ASP.NET Core 2.1, так как они по умолчанию используют более раннюю версию ANCM.

Предыдущее поведение было изменено в ASP.NET Core 3.0.1 и 3.1.0 Preview 3 с целью отмены изменений в работе ASP.NET Core 2.x. Эти изменения влияют только на приложения, находящиеся вне процесса IIS.

Как описано выше, установка ASP.NET Core 3.0.0 имела побочный результат — активацию `UseHttpsRedirection` промежуточного слоя в приложениях ASP.NET Core 2.x. В ANCM в ASP.NET Core 3.0.1 и 3.1.0 Preview 3 было внесено соответствующее изменение, поэтому их установка больше не влияет на работу приложений ASP.NET Core 2.x. Переменная среды `ASPNETCORE_HTTPS_PORT`, которая заполнялась ANCM в ASP.NET Core 3.0.0, была изменена на `ASPNETCORE_ANCM_HTTPS_PORT` в ASP.NET Core 3.0.1 и 3.1.0 Preview 3. В этих выпусках также был обновлен компонент `UseHttpsRedirection` для понимания новых и старых переменных. Обновление для ASP.NET Core 2.x не предусмотрено. В результате возвращается предыдущему поведению (отключено по умолчанию).

#### <a name="reason-for-change"></a>Причина изменения

Улучшена функциональность ASP.NET Core 3.0.

#### <a name="recommended-action"></a>Рекомендованное действие

Если все клиенты должны использовать протокол HTTPS, никаких действий не требуется. Чтобы разрешить некоторым клиентам использовать протокол HTTP, выполните одно из следующих действий.

* Удалите вызовы `UseHttpsRedirection` и `UseHsts` из метода `Startup.Configure` проекта и разверните приложение повторно.
* В файле *web.config* задайте для переменной среды `ASPNETCORE_HTTPS_PORT` пустую строку. Это изменение можно выполнить непосредственно на сервере без повторного развертывания приложения. Пример:

    ```xml
    <aspNetCore processPath="dotnet" arguments=".\WebApplication3.dll" stdoutLogEnabled="false" stdoutLogFile="\\?\%home%\LogFiles\stdout" >
        <environmentVariables>
        <environmentVariable name="ASPNETCORE_HTTPS_PORT" value="" />
        </environmentVariables>
    </aspNetCore>
    ```

`UseHttpsRedirection` по-прежнему можно:

* Активировать вручную в ASP.NET Core 2.x, задав для переменной среды `ASPNETCORE_HTTPS_PORT` соответствующий номер порта (в большинстве рабочих сценариев это порт 443).
* Отключить в ASP.NET Core 3.x, задав `ASPNETCORE_ANCM_HTTPS_PORT` с пустым строковым значением. Это значение задается таким же образом, как и в предыдущем примере `ASPNETCORE_HTTPS_PORT`.

На компьютеры, на которых выполняются приложения ASP.NET Core 3.0.0, следует установить среду выполнения ASP.NET Core 3.0.1, прежде чем устанавливать ASP.NET Core 3.1.0 Preview 3 ANCM. Это гарантирует, что `UseHttpsRedirection` будет работать правильно для приложений ASP.NET Core 3.0.

Ввиду того, что компонент ANCM является глобальным, в службе приложений Azure он развертывает по отдельному расписанию, отличному от расписания для среды выполнения. ANCM был развернут в Azure с этими изменениями после развертывания ASP.NET Core 3.0.1 и 3.1.0.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)`

-->
