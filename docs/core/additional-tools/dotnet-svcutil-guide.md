---
title: Средство Microsoft WCF dotnet-svcutil
description: Обзор инструмента Microsoft WCF dotnet-svcutil, который расширяет функциональные возможности проектов .NET Core и ASP.NET Core аналогично инструменту WCF svcutil для проектов .NET Framework.
author: mlacouture
ms.author: jralexander
ms.date: 06/04/2018
ms.openlocfilehash: c40dd9b437afe7381244b944228b6b2efe046eb2
ms.sourcegitcommit: d8bf4976eafe3289275be3811e7cb721bfff7e1e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753426"
---
# <a name="microsoft-wcf-dotnet-svcutil-tool"></a>Средство Microsoft WCF dotnet-svcutil

Средство WCF (Windows Communication Foundation) **dotnet-svcutil** — это средство .NET Core CLI, которое извлекает метаданные веб-службы в сетевом расположении или из WSDL-файла, а затем создает класс WCF, содержащий клиентские методы прокси-сервера, который используется для доступа к операциям веб-службы.

Как и [**Service Model Metadata — svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для проектов .NET Framework, **dotnet-svcutil** является программой командной строки для создания ссылки на веб-службу, совместимой с проектами .NET Core и .NET Standard.

Средство **dotnet-svcutil** служит альтернативой для поставщика подключенной службы Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), впервые представленного в Visual Studio 2017 версии 15.5. Как и .NET Core CLI, средство **dotnet-svcutil** доступно на платформах Linux, macOS и Windows.

> [!IMPORTANT]
> Ссылаться на службы следует только из надежного источника. Добавление ссылок из ненадежного источника может нарушить безопасность.

## <a name="prerequisites"></a>Предварительные требования

* [Пакет SDK для .NET Core](https://www.microsoft.com/net/download) 1.0.4 или более поздней версии
* Любой редактор кода

## <a name="getting-started"></a>Начало работы

В следующем примере описываются шаги, необходимые для добавления ссылки на веб-службу в проект консольного приложения .NET Core и вызова службы. Вы создадите консольное приложение .NET Core с именем _HelloSvcutil_ и добавите ссылку на веб-службу, которая реализует следующий контракт:

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

В этом примере предполагается, что веб-служба размещена по следующему адресу: `http://contoso.com/SayHello.svc`

В окне командной строки Windows, macOS или Linux выполните следующие действия:

1. Создайте для проекта каталог с именем _HelloSvcutil_ и сделайте его текущим каталогом, как показано в следующем примере:

```console
mkdir HelloSvcutil
cd HelloSvcutil
```

2. Создайте в этом каталоге новый проект консольного приложения C# с помощью команд [`dotnet new`](../tools/dotnet-new.md), как показано ниже:

```console
dotnet new console
```

3. Откройте в редакторе файл проекта `HelloSvcutil.csproj`, измените элемент `Project` и добавьте [пакет NuGet `dotnet-svcutil`](https://nuget.org/packages/dotnet-svcutil) в виде ссылки на средство командной строки, используя следующий код:

```xml
<ItemGroup>
  <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.0" />
</ItemGroup>
```

4. Восстановите пакет _dotnet-svcutil_ с помощью команды [`dotnet restore`](../tools/dotnet-restore.md), как показано ниже:

```console
dotnet restore
```

5. Запустите _dotnet_ с помощью команды _svcutil_, чтобы создать файл со ссылкой на веб-службу, как показано ниже:

```console
dotnet svcutil http://contoso.com/SayHello.svc
```
Созданный файл сохраняется с именем _HelloSvcutil/ServiceReference1/Reference.cs_. Средство _dotnet_svcutil_ также добавляет в проект все необходимые пакеты WCF, которые указаны в коде прокси-сервера как ссылки на пакет.

6. Восстановите пакеты WCF с помощью команды [`dotnet restore`](../tools/dotnet-restore.md), как показано ниже:

```console
dotnet restore
```

7. Откройте в редакторе файл `Program.cs` и замените автоматически созданный код метода `Main()` приведенным ниже кодом для вызова веб-службы.

```csharp
static void Main(string[] args)
{
    var client = new SayHelloClient();
    Console.WriteLine(client.HelloAsync("dotnet-svcutil").Result);
}
```

8. Запустите приложение с помощью команды [`dotnet run`](../tools/dotnet-run.md), как показано ниже:

```console
dotnet run
```
Вы увидите такой результат: "Hello dotnet-svcutil!".

Подробное описание параметров средства `dotnet-svcutil` можно получить, вызвав это средство с параметром help, как показано ниже:

```console
dotnet svcutil --help
```

## <a name="next-steps"></a>Следующие шаги

### <a name="feedback--questions"></a>Отзывы и вопросы

Если у вас появились вопросы или отзывы, [сообщите об этом на сайте GitHub](https://github.com/dotnet/wcf/issues/new). Вы также можете просмотреть имеющиеся вопросы или проблемы [в репозитории WCF на сайте GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).

### <a name="release-notes"></a>заметки о выпуске;

* Актуальные сведения о выпуске, включая описание известных проблем, см. в [заметках о выпуске](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md).

### <a name="information"></a>Сведения

* [Пакет NuGet dotnet-svcutil](https://nuget.org/packages/dotnet-svcutil)
