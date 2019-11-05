---
ms.openlocfilehash: c861d61cbbe8075db4b17a702e863336ea621f2b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198546"
---
### <a name="http-synchronous-io-disabled-in-all-servers"></a>HTTP. Отключение синхронного ввода-вывода на всех серверах

Начиная с ASP.NET Core 3,0, синхронные операции сервера по умолчанию отключены.

#### <a name="change-description"></a>Описание изменений

Параметр `AllowSynchronousIO` включает или отключает на каждом сервере синхронные API ввода-вывода, например `HttpRequest.Body.Read`, `HttpResponse.Body.Write` и `Stream.Flush`. Эти API-интерфейсы долго были причиной нехватки потоков и зависания приложений. Начиная с ASP.NET Core 3.0 предварительной версии 3, синхронные операции сервера по умолчанию отключены.

Затрагиваемые службы:

- Kestrel
- HttpSys
- IIS (внутрипроцессный)
- TestServer

Можно ожидать ошибки, аналогичные следующим:

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

Каждый сервер имеет параметр `AllowSynchronousIO`, который управляет этим поведением, и по умолчанию для всех из них используется значение `false`.

Также в качестве временного решения можно переопределять это поведение для каждого запроса. Например:

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

Если у вас возникают проблемы с `TextWriter` или другим потоком, который вызывает синхронный API в `Dispose`, обращайтесь вместо него к новому API-интерфейсу `DisposeAsync`.

Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#7644](https://github.com/aspnet/AspNetCore/issues/7644).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

По умолчанию были разрешены `HttpRequest.Body.Read`, `HttpResponse.Body.Write` и `Stream.Flush`.

#### <a name="new-behavior"></a>Новое поведение

Эти синхронные API запрещены по умолчанию:

Можно ожидать ошибки, аналогичные следующим:

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

#### <a name="reason-for-change"></a>Причина изменения

Эти синхронные API-интерфейсы долго были причиной нехватки потоков и зависания приложений. Начиная с ASP.NET Core 3.0 предварительной версии 3, синхронные операции сервера по умолчанию отключены.

#### <a name="recommended-action"></a>Рекомендуемое действие

Используйте асинхронные версии этих методов. Также в качестве временного решения можно переопределять это поведение для каждого запроса.

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.IO.Stream.Flush%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.IO.Stream.Flush`
- `Overload:System.IO.Stream.Read`
- `Overload:System.IO.Stream.Write`

-->
