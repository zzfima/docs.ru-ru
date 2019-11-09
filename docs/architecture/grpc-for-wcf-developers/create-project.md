---
title: Создание нового ASP.NET Core проекта gRPC — gRPC для разработчиков WCF
description: Узнайте, как создать проект gRPC с помощью Visual Studio или из командной строки.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: a30d19e1e48692ad68a648406d4bf369937744d7
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841663"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="55cff-103">Создание проекта ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="55cff-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="55cff-104">.NET Core поставляется с мощным средством CLI, `dotnet`, позволяющим создавать проекты и решения из командной строки и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="55cff-104">.NET Core comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="55cff-105">Это средство тесно интегрировано с Visual Studio, поэтому все также доступно с помощью привычного графического интерфейса.</span><span class="sxs-lookup"><span data-stu-id="55cff-105">The tool is closely integrated with Visual Studio, so everything is also available through the familiar GUI interface.</span></span> <span data-ttu-id="55cff-106">В этой главе будут показаны оба способа создания нового проекта ASP.NET Core gRPC: сначала с помощью Visual Studio, а затем с .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="55cff-106">This chapter will show both ways to create a new ASP.NET Core gRPC project: first with Visual Studio, then with the .NET Core CLI.</span></span>

## <a name="create-the-project-using-visual-studio"></a><span data-ttu-id="55cff-107">Создание проекта с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="55cff-107">Create the project using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55cff-108">Для разработки любого приложения ASP.NET Core 3,0 требуется Visual Studio 2019,3 или более поздняя версия с установленной рабочей нагрузкой **ASP.NET и Web Development** .</span><span class="sxs-lookup"><span data-stu-id="55cff-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019.3 or later with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="55cff-109">Создайте пустое решение с именем **традерсис** из шаблона *пустого решения* .</span><span class="sxs-lookup"><span data-stu-id="55cff-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="55cff-110">Добавьте папку решения с именем `src`, щелкните правой кнопкой мыши папку и выберите в контекстном меню команду **добавить** > **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="55cff-110">Add a Solution Folder called `src`, then right-click on the folder and choose **Add** > **New Project** from the context menu.</span></span> <span data-ttu-id="55cff-111">Введите `grpc` в поле поиска шаблона, и вы увидите шаблон проекта с именем `gRPC Service`.</span><span class="sxs-lookup"><span data-stu-id="55cff-111">Enter `grpc` in the template search box and you should see a project template called `gRPC Service`.</span></span>

![Диалоговое окно добавления нового проекта с шаблоном проекта службы gRPC](media/create-project/new-grpc-project.png)

<span data-ttu-id="55cff-113">Нажмите кнопку **Далее** , чтобы перейти в диалоговое окно **Настройка проекта** , присвойте проекту имя `TraderSys.Portfolios`и добавьте подкаталог `src` в **Расположение**.</span><span class="sxs-lookup"><span data-stu-id="55cff-113">Click **Next** to continue to the **Configure project** dialog and name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

![Диалоговое окно настройки проекта](media/create-project/configure-project.png)

<span data-ttu-id="55cff-115">Нажмите кнопку **Далее** , чтобы перейти в диалоговое окно **Новый проект gRPC** .</span><span class="sxs-lookup"><span data-stu-id="55cff-115">Click **Next** to continue to the **New gRPC project** dialog.</span></span>

![Диалоговое окно создания проекта gRPC](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="55cff-117">В настоящее время существуют ограниченные параметры для создания службы.</span><span class="sxs-lookup"><span data-stu-id="55cff-117">At present, there are limited options for the service creation.</span></span> <span data-ttu-id="55cff-118">DOCKER будет представлен позже в книге, поэтому снимите флажок для этого и просто нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="55cff-118">Docker will be introduced later in the book, so leave that checkbox unchecked for now and just click **Create**.</span></span> <span data-ttu-id="55cff-119">Будет создан первый проект ASP.NET Core 3,0 gRPC и добавлен в решение.</span><span class="sxs-lookup"><span data-stu-id="55cff-119">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="55cff-120">Если вы не хотите узнать о работе с `dotnet CLI`, перейдите к разделу [Очистка кода примера](#clean-up-the-example-code) .</span><span class="sxs-lookup"><span data-stu-id="55cff-120">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-using-the-net-core-cli"></a><span data-ttu-id="55cff-121">Создание проекта с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="55cff-121">Create the project using the .NET Core CLI</span></span>

<span data-ttu-id="55cff-122">В этом разделе рассматривается создание решений и проектов из командной строки.</span><span class="sxs-lookup"><span data-stu-id="55cff-122">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="55cff-123">Создайте решение, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="55cff-123">Create the solution as shown below.</span></span> <span data-ttu-id="55cff-124">Флаг `-o` (или `--output`) указывает выходной каталог, который будет создан в текущем каталоге, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="55cff-124">The `-o` (or `--output`) flag specifies the output directory, which will be created in the current directory if it does not exist.</span></span> <span data-ttu-id="55cff-125">Этому решению будет присвоено то же имя, что и у каталога, т. е. `TraderSys.sln`. Можно указать другое имя с помощью флага `-n` (или `--name`).</span><span class="sxs-lookup"><span data-stu-id="55cff-125">The solution will be given the same name as the directory, i.e. `TraderSys.sln`. You can provide a different name using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="55cff-126">ASP.NET Core 3,0 поставляется с шаблоном CLI для gRPC Services.</span><span class="sxs-lookup"><span data-stu-id="55cff-126">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="55cff-127">Создайте новый проект с помощью этого шаблона, поместив его в подкаталог `src`, как это соглашение для ASP.NET Core проектов.</span><span class="sxs-lookup"><span data-stu-id="55cff-127">Create the new project using this template, putting it into an `src` subdirectory as is the convention for ASP.NET Core projects.</span></span> <span data-ttu-id="55cff-128">Проект будет называться после каталога (т. е. `TraderSys.Portfolios.csproj`), если не указать другое имя с флагом `-n`.</span><span class="sxs-lookup"><span data-stu-id="55cff-128">The project will be named after the directory (i.e. `TraderSys.Portfolios.csproj`) unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="55cff-129">Наконец, добавьте проект в решение с помощью команды `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="55cff-129">Finally, add the project to the solution using the `dotnet sln` command.</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="55cff-130">Поскольку указанный каталог содержит только один файл `.csproj`, можно отказаться от указания только каталога, чтобы сохранить ввод.</span><span class="sxs-lookup"><span data-stu-id="55cff-130">Since the given directory only contains a single `.csproj` file, you can get away with specifying just the directory to save typing.</span></span>

<span data-ttu-id="55cff-131">Теперь это решение можно открыть в Visual Studio 2019, Visual Studio Code или любом другом редакторе.</span><span class="sxs-lookup"><span data-stu-id="55cff-131">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="55cff-132">Очистка кода примера</span><span class="sxs-lookup"><span data-stu-id="55cff-132">Clean up the example code</span></span>

<span data-ttu-id="55cff-133">Теперь вы создали пример службы с помощью шаблона gRPC, который был рассмотрен ранее в книге.</span><span class="sxs-lookup"><span data-stu-id="55cff-133">You've now created an example service using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="55cff-134">Это не полезно в нашем контексте торговли, поэтому мы будем изменять вещи для нашего первого проекта.</span><span class="sxs-lookup"><span data-stu-id="55cff-134">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="55cff-135">Переименование и изменение файла имени</span><span class="sxs-lookup"><span data-stu-id="55cff-135">Rename and edit the proto file</span></span>

<span data-ttu-id="55cff-136">Переименуйте файл `Protos/greet.proto` в `Protos/portfolios.proto` и откройте его в редакторе.</span><span class="sxs-lookup"><span data-stu-id="55cff-136">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto` and open it in your editor.</span></span> <span data-ttu-id="55cff-137">Удалите все после строки `package`, измените имена `option csharp_namespace`, `package` и `service` и удалите службу `SayHello` по умолчанию, чтобы код выглядел следующим образом.</span><span class="sxs-lookup"><span data-stu-id="55cff-137">Delete everything after the `package` line, then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service, so the code looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="55cff-138">Шаблон не добавляет часть пространства имен `Protos` по умолчанию, но ее добавление упрощает создание классов, создаваемых gRPC, и собственных классов, четко разделенных в коде.</span><span class="sxs-lookup"><span data-stu-id="55cff-138">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="55cff-139">Если переименовать файл `greet.proto` в интегрированной среде разработки (IDE), например Visual Studio, ссылка на этот файл будет автоматически обновлена в файле `.csproj`.</span><span class="sxs-lookup"><span data-stu-id="55cff-139">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="55cff-140">Но в другом редакторе, например Visual Studio Code, эта ссылка не обновляется автоматически, поэтому необходимо изменить файл проекта вручную.</span><span class="sxs-lookup"><span data-stu-id="55cff-140">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="55cff-141">В целевом построении gRPC имеется элемент `Protobuf` Item, позволяющий указать, какие `.proto` файлы должны быть скомпилированы и какая форма требуется для создания кода (то есть "сервер" или "клиент").</span><span class="sxs-lookup"><span data-stu-id="55cff-141">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="55cff-142">Переименование класса Гритерсервице</span><span class="sxs-lookup"><span data-stu-id="55cff-142">Rename the GreeterService class</span></span>

<span data-ttu-id="55cff-143">Класс `GreeterService` находится в папке `Services` и наследуется от `Greeter.GreeterBase`.</span><span class="sxs-lookup"><span data-stu-id="55cff-143">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="55cff-144">Переименуйте его в `PortfolioService` и измените базовый класс на `Portfolios.PortfoliosBase`.</span><span class="sxs-lookup"><span data-stu-id="55cff-144">Rename it to `PortfolioService` and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="55cff-145">Удалите `override` методы.</span><span class="sxs-lookup"><span data-stu-id="55cff-145">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="55cff-146">Существует ссылка на класс `GreeterService` в методе `Configure` в классе `Startup`.</span><span class="sxs-lookup"><span data-stu-id="55cff-146">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="55cff-147">Если вы использовали рефакторинг для переименования класса, эта ссылка должна быть обновлена автоматически.</span><span class="sxs-lookup"><span data-stu-id="55cff-147">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="55cff-148">Однако, если это не так, необходимо изменить его вручную.</span><span class="sxs-lookup"><span data-stu-id="55cff-148">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="55cff-149">В следующем разделе мы добавим функции к этой новой службе.</span><span class="sxs-lookup"><span data-stu-id="55cff-149">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="55cff-150">[Назад](migrate-wcf-to-grpc.md)
>[Вперед](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="55cff-150">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
