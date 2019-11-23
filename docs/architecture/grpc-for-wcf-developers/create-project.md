---
title: Создание нового ASP.NET Core проекта gRPC — gRPC для разработчиков WCF
description: Узнайте, как создать проект gRPC с помощью Visual Studio или из командной строки.
ms.date: 09/02/2019
ms.openlocfilehash: 992c3f57be25ae2517d41437170dc287f58934b6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967892"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a>Создание проекта ASP.NET Core gRPC

.NET Core поставляется с мощным средством CLI, `dotnet`, позволяющим создавать проекты и решения из командной строки и управлять ими. Это средство тесно интегрировано с Visual Studio, поэтому все также доступно с помощью привычного графического интерфейса. В этой главе будут показаны оба способа создания нового проекта ASP.NET Core gRPC: сначала с помощью Visual Studio, а затем с .NET Core CLI.

## <a name="create-the-project-using-visual-studio"></a>Создание проекта с помощью Visual Studio

> [!IMPORTANT]
> Для разработки любого приложения ASP.NET Core 3,0 требуется Visual Studio 2019,3 или более поздняя версия с установленной рабочей нагрузкой **ASP.NET и Web Development** .

Создайте пустое решение с именем **традерсис** из шаблона *пустого решения* . Добавьте папку решения с именем `src`, щелкните правой кнопкой мыши папку и выберите в контекстном меню команду **добавить** > **Новый проект** . Введите `grpc` в поле поиска шаблона, и вы увидите шаблон проекта с именем `gRPC Service`.

![Диалоговое окно добавления нового проекта с шаблоном проекта службы gRPC](media/create-project/new-grpc-project.png)

Нажмите кнопку **Далее** , чтобы перейти в диалоговое окно **Настройка проекта** , присвойте проекту имя `TraderSys.Portfolios`и добавьте подкаталог `src` в **Расположение**.

![Диалоговое окно настройки проекта](media/create-project/configure-project.png)

Нажмите кнопку **Далее** , чтобы перейти в диалоговое окно **Новый проект gRPC** .

![Диалоговое окно создания проекта gRPC](media/create-project/create-new-grpc-service.png)

В настоящее время существуют ограниченные параметры для создания службы. DOCKER будет представлен позже в книге, поэтому снимите флажок для этого и просто нажмите кнопку **создать**. Будет создан первый проект ASP.NET Core 3,0 gRPC и добавлен в решение. Если вы не хотите узнать о работе с `dotnet CLI`, перейдите к разделу [Очистка кода примера](#clean-up-the-example-code) .

## <a name="create-the-project-using-the-net-core-cli"></a>Создание проекта с помощью .NET Core CLI

В этом разделе рассматривается создание решений и проектов из командной строки.

Создайте решение, как показано ниже. Флаг `-o` (или `--output`) указывает выходной каталог, который будет создан в текущем каталоге, если он не существует. Этому решению будет присвоено то же имя, что и у каталога, т. е. `TraderSys.sln`. Можно указать другое имя с помощью флага `-n` (или `--name`).

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

ASP.NET Core 3,0 поставляется с шаблоном CLI для gRPC Services. Создайте новый проект с помощью этого шаблона, поместив его в подкаталог `src`, как это соглашение для ASP.NET Core проектов. Проект будет называться после каталога (т. е. `TraderSys.Portfolios.csproj`), если не указать другое имя с флагом `-n`.

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

Наконец, добавьте проект в решение с помощью команды `dotnet sln`.

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> Поскольку указанный каталог содержит только один файл `.csproj`, можно отказаться от указания только каталога, чтобы сохранить ввод.

Теперь это решение можно открыть в Visual Studio 2019, Visual Studio Code или любом другом редакторе.

## <a name="clean-up-the-example-code"></a>Очистка кода примера

Теперь вы создали пример службы с помощью шаблона gRPC, который был рассмотрен ранее в книге. Это не полезно в нашем контексте торговли, поэтому мы будем изменять вещи для нашего первого проекта.

### <a name="rename-and-edit-the-proto-file"></a>Переименование и изменение файла имени

Переименуйте файл `Protos/greet.proto` в `Protos/portfolios.proto` и откройте его в редакторе. Удалите все после строки `package`, измените имена `option csharp_namespace`, `package` и `service` и удалите службу `SayHello` по умолчанию, чтобы код выглядел следующим образом.

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> Шаблон не добавляет часть пространства имен `Protos` по умолчанию, но ее добавление упрощает создание классов, создаваемых gRPC, и собственных классов, четко разделенных в коде.

Если переименовать файл `greet.proto` в интегрированной среде разработки (IDE), например Visual Studio, ссылка на этот файл будет автоматически обновлена в файле `.csproj`. Но в другом редакторе, например Visual Studio Code, эта ссылка не обновляется автоматически, поэтому необходимо изменить файл проекта вручную.

В целевом построении gRPC имеется элемент `Protobuf` Item, позволяющий указать, какие `.proto` файлы должны быть скомпилированы и какая форма требуется для создания кода (то есть "сервер" или "клиент").

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a>Переименование класса Гритерсервице

Класс `GreeterService` находится в папке `Services` и наследуется от `Greeter.GreeterBase`. Переименуйте его в `PortfolioService` и измените базовый класс на `Portfolios.PortfoliosBase`. Удалите `override` методы.

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

Существует ссылка на класс `GreeterService` в методе `Configure` в классе `Startup`. Если вы использовали рефакторинг для переименования класса, эта ссылка должна быть обновлена автоматически. Однако, если это не так, необходимо изменить его вручную.

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

В следующем разделе мы добавим функции к этой новой службе.

>[!div class="step-by-step"]
>[Назад](migrate-wcf-to-grpc.md)
>[Вперед](migrate-request-reply.md)
